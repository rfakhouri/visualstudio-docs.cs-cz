---
title: "Diagramy závislost: Pokyny | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, dependency diagrams
- dependency diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: 2903bec7-a93b-46a6-aac6-994ac4f3f1a7
caps.latest.revision: "55"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: 6f55cbcd7e213d228a8b20f89538dfd88d8c2038
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
# <a name="dependency-diagrams-guidelines"></a>Diagramy závislost: pokyny
Popis architektury aplikace na vysoké úrovni vytvořením *závislostí diagramy* v sadě Visual Studio. Ujistěte se, že váš kód zůstává konzistentní s Tento návrh ověřením kódu s diagram závislostí. Ověření vrstev můžete použít také v procesu sestavení. V tématu [Channel 9 Video: návrh a ověřte vaší architektury pomocí závislostí diagramy](http://go.microsoft.com/fwlink/?LinkID=252073).  
  
 Tuto funkci podporovat kterou verzí sady Visual Studio najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="what-is-a-dependency-diagram"></a>Co je diagram závislostí?  
 Jako diagram tradiční architektura identifikuje diagram závislostí hlavní součásti nebo funkční jednotky návrh a jejich vzájemné závislosti. Každý uzel v diagramu, názvem *vrstvy*, představuje logické skupiny obory názvů, projektů nebo jiných artefakty. Při návrhu můžete nakreslit závislosti, které by měla existovat. Na rozdíl od tradičních architektura diagram můžete ověřit, že skutečné závislosti ve zdrojovém kódu odpovídají určený závislosti, které jste zadali. Tím, že ověření součástí regulární sestavení na [!INCLUDE[esprtfs](../code-quality/includes/esprtfs_md.md)], můžete zajistit, že kód programu pokračuje řídit architektura systému prostřednictvím budoucí změny. V tématu [diagramy závislost: referenční dokumentace](../modeling/layer-diagrams-reference.md).  
  
##  <a name="Update"></a>Postup návrhu nebo aktualizujete aplikaci s diagramy závislostí  
 Následující kroky poskytovat přehled o tom, jak používat diagramy závislosti v rámci procesu vývoje. V dalších částech v tomto tématu popisují více podrobností o jednotlivých krocích. Pokud vyvíjíte nový design, vynechejte kroky, které odkazují na existující kód.  
  
> [!NOTE]
>  Tyto kroky jsou v přibližnou pořadí. Budete pravděpodobně chtít překrývat úkoly, změnit jejich tak, aby vyhovovala vaší vlastní situaci pořadí a pokroku je na začátku každé iteraci ve vašem projektu.  
  
1.  [Vytvoření diagramu závislostí](#Create) pro celou aplikaci nebo pro vrstvu, v něm.  
  
2.  [Definovat vrstvy představující primární funkční oblasti nebo součásti](#CreateLayers) vaší aplikace. Název tyto vrstvy podle jejich funkce, například "Prezentace" nebo "Služby". Pokud máte [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] řešení, můžete přidružit jednotlivé úrovně kolekce *artefakty*, jako jsou projekty, obory názvů, soubory a tak dále.  
  
3.  [Vyhledat existující závislosti](#Generate) mezi vrstvami.  
  
4.  [Upravit vrstev a závislosti](#EditArchitecture) zobrazit aktualizovaný návrh, který má kód tak, aby odrážela.  
  
5.  [Návrh nové oblasti aplikace](#NewAreas) vytvořením vrstvy představující hlavní architektonických bloků nebo součásti a definování závislostí nelze zobrazit, jak jednotlivé úrovně používá jiné.  
  
6.  [Upravit rozložení a vzhled diagramu](#EditLayout) můžete diskuse s kolegy.  
  
7.  [Ověření kódu proti diagram závislostí](#Validate) zvýrazněte konfliktům mezi kód a architektura budete potřebovat.  
  
8.  [Aktualizujte kód tak, aby odpovídala nové architektury](#UpdateCode). Opakované vyvíjet a Refaktorovat kód, dokud ověření ukazuje ke konfliktům.  
  
9. [Zahrnují ověření vrstev v procesu sestavení](#BuildValidation) zajistit, že kód nadále dodržovat návrhu.  
  
##  <a name="Create"></a>Vytvoření diagramu závislostí  
 Diagram závislostí musí být vytvořeny uvnitř projektem modelování. Můžete přidat nový diagram závislostí do existujícího projektu modelování, vytvořte nový projekt modelování pro diagram závislostí nebo zkopírujte existující diagram závislosti v rámci stejné projektem modelování.  
  
> [!IMPORTANT]
>  Přidat, přetáhněte nebo zkopírujte existujícího diagramu závislost z projektu modelování do jiného projektu modelování nebo do jiného umístění v řešení. Diagram závislostí, který se zkopíruje tímto způsobem budou mít stejné odkazy jako původní diagram i v případě, že upravíte diagramu. To zabrání ověření vrstev z správně funguje a může způsobit další problémy, jako jsou elementy chybějící nebo jiné chyby při pokusu o otevření diagramu.  
  
 V tématu [vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md).  
  
##  <a name="CreateLayers"></a>Definovat vrstvy představující funkční oblasti nebo součásti  
 Vrstvy představují logické skupiny *artefakty*, jako jsou projekty, soubory kódu, obory názvů, třídy a metody. Můžete vytvořit vrstev z artefakty z projektů Visual C# .NET a Visual Basic .NET, nebo můžete připojit specifikace nebo plány na vrstvu pomocí propojení dokumentů, například soubory aplikace Word nebo Powerpointové prezentace. Jednotlivé úrovně zobrazí jako obdélníku v diagramu a zobrazuje počet artefaktů, které jsou propojeny s ho. Vrstva může obsahovat vnořené vrstvy, které popisují úlohy, konkrétnější.  
  
 V rámci obecných pokynů, název vrstvy podle jejich funkce, například "Prezentace" nebo "Služby". Pokud artefakty spolu vzájemně úzce souvisí, můžete je umístíte ve stejné vrstvě. Pokud artefakty mohou být aktualizovány samostatně nebo použít v samostatné aplikace, můžete je umístíte do různých vrstev. Další informace o rozvrstvení vzory, navštivte stránku trendy a postupy v [http://go.microsoft.com/fwlink/?LinkId=145794](http://go.microsoft.com/fwlink/?LinkId=145794).  
  
> [!TIP]
>  Existují určité typy artefakty, pomocí kterých můžete propojit vrstvy, ale nepodporují ověření na základě závislostí diagramu. Chcete-li zjistit, jestli artefaktu podporuje ověřování, otevřete **vrstvy Průzkumníka** prozkoumat **podporuje ověřování** vlastnost odkaz artefaktů. V tématu [zjistit existující závislosti mezi vrstvami](#Generate).  
  
 Při aktualizaci aplikace obeznámeni, můžete také vytvořit map kódu. Tyto diagramy můžete zjistit vzory a závislosti při prozkoumávání kód. Pomocí Průzkumníka řešení a prozkoumejte obory názvů a třídy, které často odpovídají dobře existující vrstvy. Přiřadíte tyto artefakty kódu vrstvy tak, že je přetáhnete v Průzkumníku řešení do diagramů závislostí. Potom můžete diagramy závislostí můžete aktualizovat kód a zachování jejich konzistence s návrhu.  
  
 Další informace:  
  
-   [Vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md)  
  
-   [Použití map kódu k ladění aplikací](../modeling/use-code-maps-to-debug-your-applications.md)  
  
-   [Mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md)  
  
##  <a name="Generate"></a>Vyhledat existující závislosti mezi vrstvami  
 Závislost existuje všude, kde artefakt, který je spojen s jednou vrstvou, odkazuje na artefakt, který je přidružen k jiné vrstvě. Třída v jedné vrstvě například deklaruje proměnnou, která má třídu v jiné vrstvě. Existující závislosti můžete zjistit pomocí zpětnou je.  
  
> [!NOTE]
>  Pro určité druhy artefaktů nelze provádět zpětnou analýzu žádných závislostí. Zpětnou analýzou například nebudou získány žádné závislosti z vrstvy nebo do ní, když je propojena s textovým souborem. Pokud chcete zobrazit, jaké artefakty mít závislosti, můžete provádět zpětnou analýzu, klikněte pravým tlačítkem na jednu nebo více vrstev a pak klikněte na tlačítko **zobrazení odkazy**. V **vrstvy Explorer**, zkontrolujte **podporuje ověřování** sloupce. Závislosti nebude zpětnou analýzou pro artefakty, pro které tomto sloupci se zobrazuje **False**.  
  
#### <a name="to-reverse-engineer-existing-dependencies-between-layers"></a>Provádět zpětnou analýzu stávající závislostí mezi vrstvami  
  
-   Vyberte vrstvu jeden nebo více vrstev, klikněte pravým tlačítkem na vybrané vrstvy a pak klikněte na tlačítko **generovat závislosti**.  
  
 Obvykle se zobrazí nějaké závislosti, které by neměly existovat. Tyto závislosti lze upravit, aby odpovídaly zamýšlenému návrhu.  
  
##  <a name="EditArchitecture"></a>Upravit vrstvy a závislosti zobrazíte určený návrhu  
 Popis změny, které máte v úmyslu provést systému nebo zamýšlené architekturu, na následujících kroků můžete upravit diagram závislostí. Můžete také zvážit provedení některých refaktoringu změny ke zlepšení struktury kódu před jeho rozšíření. V tématu [zlepšení struktury kódu](#Improving).  
  
|**K**|**Proveďte tyto kroky**|  
|------------|-----------------------------|  
|Odstranit závislost, která by neměly existovat|Klikněte na tlačítko závislost a stiskněte klávesu **odstranit**.|  
|Změna nebo omezení směru závislosti|Nastavte její **směr** vlastnost.|  
|Vytvoření nových závislostí|Použití **závislostí** a **obousměrného závislostí** nástroje.<br /><br /> Chcete-li nakreslit více závislostí, klikněte na nástroj dvakrát. Až budete hotovi, klikněte na tlačítko **ukazatel** nástroj nebo klikněte na tlačítko **ESC** klíč.|  
|Zadání toho, aby artefakty spojené s vrstvou nemohly záviset na zadaných oborech názvů|Zadejte obory názvů na vrstvě **zakázáno závislosti Namespace** vlastnost. Použijte středník (**;**) pro samostatné obory názvů.|  
|Zadání toho, aby artefakty spojené s vrstvou nesměly patřit zadanému oboru názvů|Zadejte obory názvů na vrstvě **zakázáno obory názvů** vlastnost. Použijte středník (**;**) pro samostatné obory názvů.|  
|Zadání toho, aby artefakty spojené s vrstvou musely patřit jednomu ze zadaných oborů názvů|Zadejte obor názvů na vrstvě **požadované obory názvů** vlastnost. Použijte středník (**;**) pro samostatné obory názvů.|  
  
###  <a name="Improving"></a>Zlepšení struktury kódu  
 Refaktoringu změnami jsou vylepšení, které nemají vliv chování aplikace, ale pomohou lépe změnit a v budoucnu rozšířit kód. Dobře strukturovaný kód má návrh, který se snadno abstraktní diagramu závislostí.  
  
 Například pokud vytvoříte vrstvu pro každý obor názvů v editoru kódu a pak zpětně závislosti, musí existovat minimální sadu jednosměrný závislosti mezi vrstvami. Pokud vytvoříte podrobnější diagramu pomocí třídy nebo metody jako vaše vrstvy, pak výsledek musí být také stejné vlastnosti.  
  
 Pokud tomu tak není, kód bude obtížné změnit v celé jeho životnosti a bude menší vhodný pro ověření pomocí diagramy závislostí.  
  
##  <a name="NewAreas"></a>Nové oblasti návrhu aplikace  
 Když spustíte vývoj nového projektu nebo nové oblasti v nový projekt, můžete nakreslit vrstvy a závislosti, aby bylo možné identifikovat hlavní součásti před zahájením vyvíjet kód.  
  
-   **Zobrazit osobní architektury vzory** v závislostí diagramy, pokud je to možné. Diagram závislostí, který popisuje desktopová aplikace například mohou zahrnovat vrstvy například prezentace, logiku domény a Data Store. Diagram závislostí, který obsahuje jeden funkce v rámci aplikace může mít vrstvy například Model, zobrazení a kontroler. Další informace o tyto vzory najdete v tématu [trendy a postupy: Architektura aplikace](http://go.microsoft.com/fwlink/?LinkId=145794).  
  
-   **Vytvoření artefaktu kód pro jednotlivé úrovně** například obor názvů, třídu nebo součást. Díky tomu je snazší, postupujte podle kódu a kódu artefakty propojit vrstvy. Jakmile vytvoříte každý artefaktů, připojit ho do příslušné vrstvy.  
  
-   **Nemáte Většina tříd a dalších artefaktů propojit vrstvy** protože patří do větší artefaktů, jako jsou obory názvů, které jste propojili vrstvy.  
  
-   **Vytvoření nového diagramu pro novou funkci**. Obvykle bude jeden nebo více závislostí diagramy popisující celou aplikaci. Při návrhu nové funkce v aplikaci, přidat nebo změnit stávající diagramů. Místo toho vytvořte vlastní diagram, který se vztahuje k nové části kódu. Vrstvy v nový diagram mohou zahrnovat prezentace, logiku domény a vrstvy databáze pro novou funkci.  
  
     Když vytvoříte aplikaci, kód ověří jak proti celkové diagram a podrobnější diagramu funkce.  
  
##  <a name="EditLayout"></a>Upravit rozložení prezentace a diskuzi  
 Vám pomohou identifikovat vrstvy a závislosti nebo je zabývat se členy týmu, upravte vzhled a rozložení diagramu následujícími způsoby:  
  
-   Změňte velikost, tvarů a pozice vrstev.  
  
-   Změna barvy vrstev a závislosti.  
  
    -   Vyberte jeden nebo více vrstev nebo závislosti, klikněte pravým tlačítkem a pak klikněte na tlačítko **vlastnosti**. V **vlastnosti** okně Upravit **barva** vlastnost.  
  
##  <a name="Validate"></a>Ověření kódu proti diagramu  
 Pokud jste upravili diagramu, můžete ověřit ho s kódem kdykoli ručně nebo automaticky při každém spuštění místní sestavení nebo [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)].  
  
 Další informace:  
  
-   [Ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md)  
  
-   [Zahrnují ověření vrstev v procesu sestavení](#BuildValidation)  
  
##  <a name="UpdateCode"></a>Aktualizujte kód tak, aby odpovídala nové architektury  
 Obvykle chyb se zobrazí při prvním ověření kódu proti diagramu aktualizované závislostí. Tyto chyby může mít několik příčin:  
  
-   Artefakt je přiřazen nesprávné vrstvě. V tomto případě přesuňte artefakt.  
  
-   Artefakt, jako je například třída, používá jiné třídy způsobem, který je v konfliktu s architekturou. V tomto případě refaktorujte kód a odeberte závislost.  
  
 Chcete-li tyto chyby odstranit, aktualizujte kód, dokud se během ověřování neobjeví žádné chyby. Je to obvykle iterativní proces. Další informace o těchto chybách naleznete v části [ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md).  
  
> [!NOTE]
>  Jak vyvíjet nebo Refaktorovat kód, můžete mít nový artefaktů a propojit diagram závislostí. Ale to nemusí být nutné, například když máte vrstvy, které představují existující obory názvů a další materiály nový kód přidá jenom na tyto obory názvů.  
  
 Během procesu vývoje můžete chtít potlačit některé vykázané konflikty během ověřování. Například můžete chtít potlačit chyby, které již řešíte nebo které nejsou relevantní k danému scénáři. Pokud potlačíte chybu, je dobrým zvykem přihlásit pracovní položku [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]. K provedení této úlohy, najdete v části [ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md).  
  
##  <a name="BuildValidation"></a>Zahrnují ověření vrstev v procesu sestavení  
 Zajistit, že budoucí změny v kódu odpovídají diagramy závislostí, zahrnují ověření vrstev procesu standardní build vaše řešení. Vždy, když ostatní členové týmu sestavte řešení, případné rozdíly mezi diagram závislosti a závislosti v kódu se ohlásí jako chyby sestavení. Další informace o ověření vrstev, včetně v procesu sestavení najdete v tématu [ověřování kódu pomocí diagramů závislostí](../modeling/validate-code-with-layer-diagrams.md).  
  
## <a name="see-also"></a>Viz také  
 [Diagramy závislost: referenční dokumentace](../modeling/layer-diagrams-reference.md)   
 [Vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md)
