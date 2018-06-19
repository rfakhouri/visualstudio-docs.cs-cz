---
title: Skriptovací rozhraní systému Windows | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c750627-6797-4857-9f5e-e5f54371f83c
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 200a1ac1bf273e2515e1e17b6f83c2020ff9884d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24796497"
---
# <a name="windows-script-interfaces"></a>Skriptovací rozhraní systému Windows
Skriptovací rozhraní systému Windows Microsoft umožňují pro aplikace pro přidání skriptování a automatizace OLE. Skriptování hostitelů, které jsou závislé na skriptu Windows můžete použít skriptovacích strojů z více zdrojů a dodavatelé ke správě skriptování mezi součástmi. Implementace samotný skript – jazyk, syntaxe, trvalém formátu, model spouštění a tak dále – je zbývající ke skriptu dodavatele.  
  
 Dokumentaci k Windows Script je rozdělené do následujících částí:  
  
 [Moduly Windows Script Host](../winscript/windows-script-hosts.md)  
  
 [Skriptovací stroje systému Windows](../winscript/windows-script-engines.md)  
  
 [Přehled ladění aktivních skriptů](../winscript/active-script-debugging-overview.md)  
  
 [Přehled profilace aktivních skriptů](../winscript/active-script-profiling-overview.md)  
  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../winscript/reference/windows-script-interfaces-reference.md)  
  
## <a name="windows-script-background"></a>Skript pozadí systému Windows  
 Rozhraní Windows skriptů rozdělit do dvou kategorií: Windows Script Host a moduly Windows Script. Hostitel vytvoří skriptovacího stroje a volání na modul ke spouštění skriptů. Příklady Windows Script Host:  
  
-   Microsoft Internet Explorer  
  
-   Internetové nástroje pro tvorbu  
  
-   Prostředí  
  
 Windows skriptovacích strojů, které mohou být vytvořeny pro libovolném jazyce nebo běhové prostředí, včetně:  
  
-   Microsoft Visual Basic Scripting Edition (VBScript)  
  
-   Perl  
  
-   Lisp  
  
 Chcete-li implementace hostitele co nejpružnější, je k dispozici automatizace OLE obálku pro skriptům v systému Windows. Na hostitele, který používá tento objekt obálky k vytvoření instance skriptovacího stroje však nemá míru kontroly nad obor názvů běhu, trvalost modelu a tak dále, kdyby se přímo použít skript Windows.  
  
 Modul Windows Script návrh izoluje prvky rozhraní tak, aby nonauthoring hostitele (například s prohlížeči a prohlížeče) a moduly skriptu (například VBScript) je možné mít lightweight vyžaduje jenom v prostředí pro vytváření obsahu.  
  
## <a name="windows-script-basic-architecture"></a>Základní architektura skript systému Windows  
 Následující obrázek ukazuje interakce mezi Windows Script host a modul Windows Script.  
  
 V následujícím seznamu jsou uvedeny kroky interakce mezi hostiteli a modul.  
  
1.  Vytvořte projekt. Hostitel načte projektu nebo dokumentu. (Tento krok není konkrétní do skriptu Windows, ale jsou zde uvedeny pro úplnost.)  
  
2.  Vytvořte modul Windows Script. Volání hostitele `CoCreateInstance` Pokud chcete vytvořit nový modul Windows Script, určení konkrétní skriptovací stroje použít identifikátor třídy (CLSID). Například prohlížeč HTML v aplikaci Internet Explorer obdrží identifikátor třídy skriptovací stroj prostřednictvím CLSID = atribut HTML \<OBJEKT > značky.  
  
3.  Načítání skriptu. Pokud obsah skriptů jsou držena formou, zavolá hostitele skriptovací stroj `IPersist*::Load` metodu pro informační kanál skriptu úložiště, datový proud nebo vlastnost kontejneru. Jinak, hostitel používá. buď `IPersist*::InitNew` nebo [IActiveScriptParse::InitNew](../winscript/reference/iactivescriptparse-initnew.md) metodu pro vytvoření skript hodnotu null. Na hostitele, který udržuje skript jako text můžete použít [IActiveScriptParse::ParseScriptText](../winscript/reference/iactivescriptparse-parsescripttext.md) ke kanálu skriptovacího stroje text skriptu, po volání `IActiveScriptParse::InitNew`.  
  
4.  Přidejte pojmenované položky. Pro každou nejvyšší úrovně s názvem položku (například stránky a formulářů) importovat do oboru názvů skriptovací stroje, volá hostitele [IActiveScript::AddNamedItem](../winscript/reference/iactivescript-addnameditem.md) metodu pro vytvoření položku v oboru názvů stroje. Tento krok není nutný, pokud nejvyšší úrovně s názvem položky jsou již součástí trvalý stav skriptu načíst v kroku 3. Hostitel nepoužívá `IActiveScript::AddNamedItem` přidat z dílčích úkolů s názvem položky (například ovládací prvky na stránce HTML); místo toho modul nepřímo získává z dílčích úkolů položek z nejvyšší úrovně položky pomocí hostitele `ITypeInfo` a `IDispatch` rozhraní.  
  
5.  Spusťte skript. Hostitel způsobí, že modul spustit skript nastavením příznaku SCRIPTSTATE_CONNECTED [IActiveScript::SetScriptState](../winscript/reference/iactivescript-setscriptstate.md) metoda. Toto volání by pravděpodobně práci žádné skriptovací stroj konstrukce, včetně statické vazby, zapojování k událostem (viz níže) a provádění kódu, způsobem, který je podobný skriptované `main()` funkce.  
  
6.  Získáte informace o položce. Pokaždé, když skriptovací stroj je potřeba přidružit symbol položku nejvyšší úrovně, zavolá [IActiveScriptSite::GetItemInfo](../winscript/reference/iactivescriptsite-getiteminfo.md) metoda, která vrátí informace o daná položka.  
  
7.  Připojení událostí. Před spuštěním vlastního skriptu, skriptovací stroj připojí k událostem všechny relevantní objekty prostřednictvím `IConnectionPoint` rozhraní.  
  
8.  Vyvolání metody a vlastnosti. Jako skript se spustí, skriptovací stroj rozpoznává odkazy na metody a vlastnosti na pojmenovaných objektů prostřednictvím `IDispatch::Invoke` nebo jiných standardních mechanismů vazby OLE.  
  
## <a name="windows-script-terms"></a>Podmínky skriptu Windows  
 Tento seznam obsahuje definice skriptování související termínů použitých v tomto dokumentu.  
  
|Termín|Definice|  
|----------|----------------|  
|Objekt kódu|Instance vytvořené skriptovací stroj, který je přidružen pojmenovanou položku, jako je například modul za formuláře v jazyce Visual Basic nebo třídy C++ spojené s pojmenovanou položku. Pokud možno toto je objekt OLE modelu COM (Component Object), který podporuje automatizace OLE tak hostitele nebo jiné entity bez skriptu můžete upravit objekt kódu.|  
|Položka s názvem|Objekt OLE COM (pokud možno jeden, který podporuje automatizace OLE) které hostitel považuje za zajímavé pro skript. Mezi příklady patří stránky HTML a prohlížeč v webový prohlížeč, dokument a dialogová okna v aplikaci Microsoft Word.|  
|Skript|Data, která tvoří program, který běží skriptovacího stroje. Skript může být jakékoli souvislý spustitelné data, včetně částí textu, bloky `pcode`, nebo dokonce kódy spustitelné bajtů specifické pro počítač. Hostitel načte skript do skriptovacího stroje prostřednictvím jednoho z `IPersist*` rozhraní nebo pomocí [IActiveScriptParse –](../winscript/reference/iactivescriptparse.md) rozhraní.|  
|Skriptovací stroje|OLE objekt, který zpracovává skripty. Skriptovací stroje implementuje [IActiveScript –](../winscript/reference/iactivescript.md) a volitelně [IActiveScriptParse –](../winscript/reference/iactivescriptparse.md) rozhraní.|  
|Hostitelů skriptování|Aplikace nebo program, který vlastní modul Windows Script. Implementuje hostitele [iactivescriptsite –](../winscript/reference/iactivescriptsite.md) a volitelně [iactivescriptsitewindow –](../winscript/reference/iactivescriptsitewindow.md) rozhraní.|  
|Skriptlet|Část skript, který získá připojen k objektu pomocí [IActiveScriptParse –](../winscript/reference/iactivescriptparse.md) rozhraní. Agregační kolekce skriptlety je skript.|  
|Skriptovací jazyk|Jazyk, ve kterém je skript napsané (VBScript, např.) a sémantiku daného jazyka.|  
  
## <a name="see-also"></a>Viz také  
 [Skriptovací rozhraní systému Windows](../winscript/windows-script-interfaces.md)