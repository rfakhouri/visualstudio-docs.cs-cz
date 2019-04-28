---
title: Windows skriptovací stroje | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows script engines
ms.assetid: e576853d-7252-4eb9-81eb-9d5bb7626ab4
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1acbc364e9ee2a5a4911564eb6d2c7d4c34de458
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63415996"
---
# <a name="windows-script-engines"></a>Skriptovací stroje systému Windows
K implementaci Microsoft Windows skriptovací stroj, vytvořte objekt OLE COM, který podporuje následující rozhraní.  
  
|||  
|-|-|  
|Rozhraní|Popis|  
|[IActiveScript](../winscript/reference/iactivescript.md)|Poskytuje základní možnosti skriptování. Implementace tohoto rozhraní je povinný.|  
|[IActiveScriptParse](../winscript/reference/iactivescriptparse.md)|Umožňuje přidat text skriptu, vyhodnocujte výrazy a tak dále. Implementace tohoto rozhraní je volitelné. Nicméně pokud není implementována, skriptovací stroj musí implementovat jedno z rozhraní IPersist *-li načíst skript.|  
|IPersist*|Poskytuje podporu trvalosti. Provádění splnit aspoň jednu z následujících rozhraní je vyžadována, pokud [IActiveScriptParse –](../winscript/reference/iactivescriptparse.md) není implementována.<br /><br /> IPersistStorage: Poskytuje podporu pro DATA = {url} atributu ve značce objektu.<br /><br /> IPersistStreamInit: Poskytuje podporu pro stejný jako `IPersistStorage` a také DATA = "datový proud bajtů kódovaný řetězec" atribut ve značce objektu.<br /><br /> IPersistPropertyBag: Poskytuje podporu pro PARAMETRECH = atribut ve značce objektu.|  
  
> [!NOTE]
> Je možné, že skriptovací stroj nebude nikdy volána po uložení nebo obnovení stavu skriptu prostřednictvím `IPersist*`. Místo toho [IActiveScriptParse –](../winscript/reference/iactivescriptparse.md) používá volání [IActiveScriptParse::InitNew](../winscript/reference/iactivescriptparse-initnew.md) vytvoření prázdné skriptu, pak skriptlety se přidají a připojených na události s [IActiveScriptParse –:: AddScriptlet](../winscript/reference/iactivescriptparse-addscriptlet.md) a obecné kód se přidá s [IActiveScriptParse::ParseScriptText](../winscript/reference/iactivescriptparse-parsescripttext.md). Skriptovací stroj musí však plně implementovat alespoň jedno `IPersist*` rozhraní (pokud možno `IPersistStreamInit`), protože ostatní hostovat aplikace se může pokusit provést jejich použití.  
  
 Následující části popisují implementaci modul Windows Scripting podrobněji.  
  
 Zobrazit [referenční dokumentace skriptovacích rozhraní Windows](../winscript/reference/windows-script-interfaces-reference.md) Další informace.  
  
## <a name="registry-standard"></a>Standardní registru  
 Modul skriptu Windows můžete identifikovat pomocí identifikátorů kategorie. Skript Windows aktuálně definuje dva identifikátory kategorie.  
  
|||  
|-|-|  
|Kategorie|Popis|  
|CATID_ActiveScript|Označuje, že identifikátory tříd (CLSID) jsou Windows skriptovacích strojů, které podporují minimálně [IActiveScript –](../winscript/reference/iactivescript.md) rozhraní a mechanismus trvalého ( `IPersistStorage`, `IPersistStreamInit`, nebo IPersistPropertyBag rozhraní).|  
|CATID_ActiveScriptParse|Označuje, že jsou CLSID Windows skriptovacích strojů, které podporují minimálně [IActiveScript –](../winscript/reference/iactivescript.md) a [IActiveScriptParse –](../winscript/reference/iactivescriptparse.md) rozhraní.|  
  
 I když [IActiveScriptParse –](../winscript/reference/iactivescriptparse.md) není true trvalost mechanismus, podporuje [IActiveScriptParse::InitNew](../winscript/reference/iactivescriptparse-initnew.md) metodu, která je funkčně srovnatelný s `IPersist*::InitNew`.  
  
## <a name="script-engine-states"></a>Stavy se skriptovacím modulem  
 V každém okamžiku může být Windows skriptovací stroj v jednom z několika stavů.  
  
|||  
|-|-|  
|Stav|Popis|  
|Neinicializované|Skript nebyl inicializován nebo načíst pomocí rozhraní IPersist * nebo nemá [iactivescriptsite –](../winscript/reference/iactivescriptsite.md) sady rozhraní. Skriptovací stroj se obecně nedá použít v tomto stavu až načtení skriptu.|  
|inicializován|Tento skript byl inicializován s `IPersist*` rozhraní a má [iactivescriptsite –](../winscript/reference/iactivescriptsite.md) rozhraní sady, ale není připojený k hostiteli objekty a zpracování událostí. Mějte na paměti, že tento stav jednoduše znamená, že `IPersist*::Load`, `IPersist*::InitNew`, nebo [IActiveScriptParse::InitNew](../winscript/reference/iactivescriptparse-initnew.md) metoda byla dokončena a že [IActiveScript::SetScriptSite](../winscript/reference/iactivescript-setscriptsite.md) má – metoda byla volána. Modul nelze spustit kód v tomto režimu. Kód, který projde hostitele k němu přes modul zařadí do fronty [IActiveScriptParse::ParseScriptText](../winscript/reference/iactivescriptparse-parsescripttext.md) metoda a spouští kód po přechodu do spuštěného stavu.<br /><br /> Protože jazyky můžou výrazně lišit v sémantice, skriptovacích strojů nejsou vyžadovány pro podporu tohoto přechodu stavu. Motory, které podporují [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md) metodu podporovali však tento přechod stavu. Hostitelé musí připravit pro tento přechod a přijmout vhodná opatření: vydání aktuální skriptovací stroj, vytvořte nový skriptovací stroj a volání `IPersist*::Load`, `IPersist*::InitNew`, nebo [IActiveScriptParse::InitNew](../winscript/reference/iactivescriptparse-initnew.md) (a může být také volat [IActiveScriptParse::ParseScriptText](../winscript/reference/iactivescriptparse-parsescripttext.md)). Použití tohoto přechodu je považovat za optimalizace výše uvedených kroků. Všimněte si, že všechny skriptovací stroj má získat informace o názvech položek s názvem a typu informací, které popisují s názvem položky zůstávají platné.<br /><br /> Protože jazyky se velmi liší, definování přesné sémantiku tohoto přechodu je obtížné. Minimálně skriptovací stroj musí odpojit od všech událostí a uvolnit všechny odkazy SCRIPTINFO_IUNKNOWN získán voláním [IActiveScriptSite::GetItemInfo](../winscript/reference/iactivescriptsite-getiteminfo.md) metody. Po spuštění skriptu znovu, musíte modul znovu získat tyto ukazatele. Skriptovací modul by měl také obnovit skript počáteční stav, který je vhodný pro jazyk. Jazyk VBScript, například obnoví všechny proměnné a uchovává všechny kódu dynamicky přidávat voláním [IActiveScriptParse::ParseScriptText](../winscript/reference/iactivescriptparse-parsescripttext.md) nastaven příznak SCRIPTTEXT_ISPERSISTENT. Další jazyky může být nutné zachovat aktuální hodnoty (například Lisp, protože neexistuje žádný kód/data oddělení) nebo obnovit do známého stavu (to zahrnuje jazyků s staticky inicializované proměnné).<br /><br /> Všimněte si, že přechod do stavu spuštěno, musí mít stejnou sémantiku (to znamená, ho měli nechat skriptovací stroj ve stejném státě) jako volání funkce `IPersist*::Save` uložte skriptovací stroj a potom voláním `IPersist*::Load` načíst nový skriptovací stroj; tyto akce by měly mít stejnou sémantiku jako [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md). Skriptovací stroje, které se ještě nepodporují `IActiveScript::Clone` nebo `IPersist*` měli pečlivě zvažte, jak by měla chovat přechod do stavu spuštěno, tak, aby tento přechod nebude porušují výše uvedené podmínky, pokud `IActiveScript::Clone` nebo `IPersist*` později byla přidána podpora.<br /><br /> Během tohoto přechodu do stavu spuštěno skriptovací stroj se odpojit od jímky událostí po příslušné destruktory a atd., jsou spouštěny ve skriptu. Abyste nemuseli tyto destruktory proveden, hostitele můžete nejprve přesunout skript v odpojeném stavu před přesunutím do spuštěného stavu.<br /><br /> Použití [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) tak, aby skončí zrušit spuštěné vlákno skript bez čekání na události aktuální a tak dále.|  
|Spuštění|Přechod z inicializovaném stavu na spuštěném stavu způsobí, že modul spustit jakýkoli kód, který byl zařazen do fronty v inicializovaném stavu. Modul může spustit kód ve spuštěném stavu, ale není připojen k žádné události přidané prostřednictvím [IActiveScript::AddNamedItem](../winscript/reference/iactivescript-addnameditem.md) metody. Modul může spustit kód voláním rozhraní IDispatch získaných [IActiveScript::GetScriptDispatch](../winscript/reference/iactivescript-getscriptdispatch.md) metodu, nebo pomocí volání [IActiveScriptParse::ParseScriptText](../winscript/reference/iactivescriptparse-parsescripttext.md). Je možné, že další inicializace na pozadí (postupné načítání) je stále probíhají a volání [IActiveScript::SetScriptState](../winscript/reference/iactivescript-setscriptstate.md) metody s příznakem SCRIPTSTATE_CONNECTED může způsobit, že skript blokování až do dokončení inicializace.|  
|Připojení|Skript je načten a připojen pro zpracování událostí z hostitele objektů. Pokud je přechod z inicializovaném stavu, přechodu by měl skriptovací stroj prostřednictvím spuštěném stavu, provádí se vším, před zadáním stav připojení a připojení k události.|  
|Odpojení|Skript je načten a má stav za běhu, ale je dočasně odpojen od zpracování událostí z hostitele objektů. To lze provést buď logicky (ignorování událostí přijatých) nebo fyzicky (IConnectionPoint::Unadvise při volání na odpovídající spojovací body). Pokud je přechod z inicializovaném stavu, přechodu by měl skriptovací stroj prostřednictvím spuštěném stavu, provádí se vším, před vstupem odpojeném stavu. Jímky událostí, které jsou v průběhu jsou dokončeny před změny stavu (použijte [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) zrušit spuštěné vlákno skriptu). Tento stav se liší od inicializovaném stavu, přechodu na tento stav způsobit skript, který chcete obnovit, není resetovat stav běhu skriptu a inicializační proceduru skriptu není spuštěn.|  
|Uzavřeno|Skript se zavřel. Skriptovací stroj už funguje a vrátí chyby pro většinu metod.|  
  
 Následující obrázek znázorňuje vztahy mezi různými státy skriptovací stroj a zobrazuje metody, které způsobují přechodů z jednoho stavu do druhého.  
  
 Následující obrázek znázorňuje akce, které provádí skriptovací stroj při různých přechodů.  
  
## <a name="scripting-engine-threading"></a>Skriptovací modul dělení na vlákna  
 Protože Windows skriptovací stroj je použít v mnoha prostředích, je důležité udržovat možné nejpružnější modelu jeho spuštění. Na serveru hostitele může například nutné zachovat návrh s více vlákny při použití skriptu Windows efektivním způsobem. Ve stejnou dobu by neměly být burdened hostitele, který nepoužívá dělení na vlákna, jako je například Typická aplikace s dělení na vlákna správy. Skript Windows této rovnováhy dosahuje omezení způsobech volných vláken skriptovací stroj volat zpět na hostitele, uvolnění hostitele z této zatížení.  
  
 Skriptovacích strojů použít na servery jsou obvykle implementovány jako objekty modelu COM zdarma threading. To znamená, že metody [IActiveScript –](../winscript/reference/iactivescript.md) rozhraní a jeho přidružené rozhraní nelze volat z libovolného vlákna v procesu, bez zařazování. (Bohužel, zároveň to znamená, že skriptovací stroj musí být implementován jako v procesový server, protože OLE nepodporuje aktuálně meziprocesovou zařazování volných vláken objektů.) Synchronizace zodpovídá za skriptovací stroj. Skriptovací stroje, které nejsou interně vícenásobné, nebo jazykové modely, které nejsou s více vlákny může být stejně snadné jako serializace přístup ke skriptovací stroj s mutex synchronizace. Samozřejmě některé metody, jako například [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md), nesmí být serializován tímto způsobem tak, aby zablokované skriptu lze ukončit z jiného vlákna.  
  
 Fakt, který [IActiveScript –](../winscript/reference/iactivescript.md) je obvykle volných vláken obecně vyplývá, že [iactivescriptsite –](../winscript/reference/iactivescriptsite.md) rozhraní a model objektu hostitele by měl být typu free i. Implementace hostitele mohou mít poměrně složité, zejména v obvyklém případě, kdy hostitel je aplikace s jedním vláknem založené na Windows s s jedním vláknem nebo apartment model ovládacích prvků ActiveX v jeho objektový model. Z tohoto důvodu se tato omezení jsou umístěny na použití skriptovací stroj [iactivescriptsite –](../winscript/reference/iactivescriptsite.md):  
  
 Skript lokality je volána vždy v kontextu vlákna hostitele. To znamená, skriptování modul nikdy volání skriptu lokality v kontextu vlákna, které skriptovací stroj vytvořil, ale pouze v rámci skriptovací modul metodu, která byla volána z hostitele prostřednictvím [IActiveScript –](../winscript/reference/iactivescript.md) a jeho odvozené prostřednictvím objektu, odeslání vystavené skriptovací stroj, prostřednictvím zpráv Windows nebo ze zdroje událostí v objektovém modelu hostitele.  
  
 Skript webu nikdy volat v rámci kontextu metodu jednoduché vláknu stavu ovládacího prvku (například [IActiveScript::InterruptScriptThread](../winscript/reference/iactivescript-interruptscriptthread.md) metoda) nebo z [IActiveScript::Clone](../winscript/reference/iactivescript-clone.md) Metoda.  
  
## <a name="see-also"></a>Viz také  
 [Skriptovací rozhraní systému Windows](../winscript/windows-script-interfaces.md)
