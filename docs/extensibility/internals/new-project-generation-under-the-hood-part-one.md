---
title: "Nové generace projektu: Pod pokličkou, první část | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio], new project dialog
- projects [Visual Studio], new project generation
ms.assetid: 66778698-0258-467d-8b8b-c351744510eb
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: efe08d9e23f1a77fd68df2bdba4389e7b7955b11
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="new-project-generation-under-the-hood-part-one"></a>Nové generace projektu: Pod pokličkou, první část
Někdy představit o tom, jak vytvořit vlastní typ projektu? Zajímat, co se ve skutečnosti stane, když vytvoříte nový projekt? Umožňuje provést funkce Náhled pod pokličkou a zjistěte, co se skutečně děje.  
  
 Existuje několik úloh, které souřadnice Visual Studio:  
  
-   Zobrazuje strom všechny typy dostupných projektů.  
  
-   Zobrazí seznam šablon aplikací pro každý typ projektu a umožňuje vybrat jednu.  
  
-   Shromáždí informace o projektu pro aplikaci, například název projektu a cestu.  
  
-   Pak předá tyto informace k objektu pro vytváření projektu.  
  
-   Vygeneruje položky projektu a složky v aktuálním řešení.  
  
## <a name="the-new-project-dialog-box"></a>Dialogového okna Nový projekt  
 Všechny začíná, když vyberete typ projektu pro nový projekt. Začněme tím, že kliknete na **nový projekt** na **souboru** nabídky. **Nový projekt** zobrazí se dialogové okno, vypadající něco takto:  
  
 ![Dialogové okno Nový projekt](../../extensibility/internals/media/newproject.gif "NewProject")  
  
 Se podíváme blíže. **Typy projektů** stromu uvádí různé typy projektů, můžete vytvořit. Když vyberete jako typ projektu **Visual C# Windows**, zobrazí se seznam šablon aplikací, které vám pomůžou začít. **Visual Studio – nainstalované šablony** jsou nainstalované Visual Studio a jsou dostupné pro všechny uživatele počítače. Nové šablony, které vytváříte nebo shromažďovat mohou být přidány do **šablony** a jsou dostupné pouze pro vás.  
  
 Když vyberete některou šablonu jako **aplikace Windows**, popis typ aplikace se zobrazí v dialogovém okně; v tomto případě **projektu pro vytváření aplikací s uživatelským rozhraním Windows**.  
  
 V dolní části **nový projekt** dialogové okno, zobrazí se několik ovládacích prvků, které zjištění dalších informací. Ovládací prvky zobrazí závisí na typu projektu, ale obecně obsahují projektu **název** textového pole **umístění** textového pole a související **Procházet** tlačítko a **Název řešení** textového pole a související **vytvořit adresář pro řešení** zaškrtávací políčko.  
  
## <a name="populating-the-new-project-dialog-box"></a>Naplnění dialogového okna Nový projekt  
 Kde se **nový projekt** dialogové okno získat informace o z? Existují dva mechanismy v zde práci, jeden z nich zastaralé. **Nový projekt** dialogové okno kombinuje a informacemi získanými z obou mechanismy.  
  
 Starší (nepoužívané) metoda používá položky systémového registru a .vsdir soubory. Tento mechanismus se spustí při otevření sady Visual Studio. Novější metoda používá soubory .vstemplate. Tento mechanismus se spustí v případě, že je inicializovat Visual Studio, například v spuštěním  
  
```  
devenv /setup  
```  
  
 or  
  
```  
devenv /installvstemplates  
```  
  
### <a name="project-types"></a>Typy projektů  
 Pozice a názvy **typy projektů** hlavní uzly, jako například **Visual C#** a **jiné jazyky**, je dáno položky systémového registru. Uspořádání podřízených uzlů, jako například **databáze** a **Smart Device**, odpovídá hierarchii složek, které obsahují odpovídající soubory .vstemplate. Podívejme se na kořenové uzly nejdřív.  
  
#### <a name="project-type-root-nodes"></a>Projekt typu kořenové uzly  
 Když [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] je inicializován, prochází podklíčů klíče registru systému HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\14.0\NewProjectTemplates\TemplateDirs sestavení a název kořenové uzly **typyprojektů** stromu. Tyto informace se uloží do mezipaměti pro pozdější použití. Podívejte se na TemplateDirs\\{FAE04EC1-301F-11D3-BF4B-00C04F79EFBC} \\ /1 klíč. Každá položka je identifikátor GUID VSPackage. Název podklíče (/ 1) je ignorována, ale jeho přítomnosti označuje, že je to **typy projektů** kořenový uzel. Kořenový uzel pak může mít několik podklíčů, které řídí jeho zobrazení **typy projektů** stromu. Podívejme se na některé z nich.  
  
##### <a name="default"></a>(Výchozí)  
 Toto je ID prostředku lokalizované řetězce, který názvy kořenového uzlu. Řetězec prostředku je umístěn ve satelitní knihovny DLL vybraná VSPackage GUID.  
  
 V příkladu je identifikátor GUID VSPackage  
  
 {FAE04EC1-301F-11D3-BF4B-00C04F79EFBC}  
  
 ID prostředku (výchozí hodnota) kořenového uzlu a (/ 1) je #2345  
  
 Pokud vyhledání identifikátoru GUID v klíči blízkým balíčky a vyhledejte podklíč SatelliteDll, můžete nějakého najít cestu sestavení, které obsahuje řetězec prostředku:  
  
 \<Cesta instalace Visual Studio > \VC#\VCSPackages\1033\csprojui.dll  
  
 Chcete-li to ověřit, otevřete Průzkumníka souborů a přetáhněte csprojui.dll do adresáře sady Visual Studio... Tabulky řetězců zobrazuje, že má prostředek #2345 titulek **Visual C#**.  
  
##### <a name="sortpriority"></a>SortPriority  
 Tato hodnota určuje pozici kořenový uzel ve **typy projektů** stromu.  
  
 REG_DWORD SortPriority 0x00000014 (20)  
  
 Čím nižší je číslo prioritu, tím vyšší pozice ve stromové struktuře.  
  
##### <a name="developeractivity"></a>DeveloperActivity  
 Pokud se nachází tento podklíč, pozice kořenového uzlu je řízena pomocí dialogu nastavení Developer. Například  
  
 REG_SZ DeveloperActivity VC #  
  
 Určuje, že Visual C# kořenový uzel Pokud Visual Studio je nastavený pro [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] vývoj. Jinak bude podřízený uzel **jiné jazyky**.  
  
##### <a name="folder"></a>Folder  
 Pokud se nachází tento podklíč, kořenového uzlu stane podřízený uzel do zadané složky. Zobrazí se seznam možných složky pod klíčem  
  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\NewProjectTemplates\PseudoFolders  
  
 Například má položka databázové projekty složky klíč, který odpovídá položce jiné typy projektů v PseudoFolders. Ano, v **typy projektů** stromu **databázové projekty** bude podřízený uzel **jiné typy projektů**.  
  
#### <a name="project-type-child-nodes-and-vstdir-files"></a>Typ podřízené uzly a .vstdir soubory projektu  
 Pozice v podřízené uzly **typy projektů** stromu odpovídá hierarchii složek ve složkách ProjectTemplates. Pro počítač šablony (**Visual Studio – nainstalované šablony**), obvyklé umístění je \Program Files\Microsoft 14.0\Common7\IDE\ProjectTemplates\ Visual Studio a pro uživatele šablony (**Moje šablony**), obvyklé umístění je \My Documents\Visual Studio 14.0\Templates\ProjectTemplates\\. Hierarchie složky z těchto dvou umístění jsou sloučeny vytvořit **typy projektů** stromu.  
  
 Pro sadu Visual Studio s C# nastaveními vývojáře **typy projektů** stromu vypadá přibližně takto:  
  
 ![Typy projektů](../../extensibility/internals/media/projecttypes.png "ProjectTypes")  
  
 Odpovídající složce ProjectTemplates vypadá takto:  
  
 ![Šablony projektu](../../extensibility/internals/media/projecttemplates.png "ProjectTemplates")  
  
 Když **nový projekt** otevře se dialogové okno, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prochází složce ProjectTemplates a znovu vytvoří jeho struktury v **typy projektů** stromu s některé změny:  
  
-   Kořenový uzel ve **typy projektů** určuje stromu šablona aplikací.  
  
-   Název uzlu je možné lokalizovat a může obsahovat speciální znaky.  
  
-   Pořadí řazení lze změnit.  
  
##### <a name="finding-the-root-node-for-a-project-type"></a>Hledání na kořenový uzel pro typ projektu  
 Když Visual Studio prochází ProjectTemplates složek, otevře se všechny soubory .zip a extrahuje soubory .vstemplate. Soubor .vstemplate používá soubor XML k popisu šablony aplikace. Další informace najdete v tématu [nové generace projektu: pod pokličkou, část dvě](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md).  
  
 \<ProjectType > Značka Určuje typ projektu pro aplikaci. Například soubor \CSharp\SmartDevice\WindowsCE\1033\WindowsCE-EmptyProject.zip obsahuje soubor EmptyProject.vstemplate, který má tuto značku:  
  
```  
<ProjectType>CSharp</ProjectType>  
```  
  
 \<ProjectType > značky a není podsložky ve složce ProjectTemplates určuje aplikace kořenový uzel ve **typy projektů** stromu. V příkladu by systém Windows CE aplikace se objeví pod **Visual C#** kořenový uzel, a i v případě, že byste chtěli přesuňte složku WindowsCE VisualBasic složku, systém Windows CE aplikace stále by se objeví pod  **Visual C#** kořenový uzel.  
  
##### <a name="localizing-the-node-name"></a>Lokalizace je název uzlu  
 Když Visual Studio prochází ProjectTemplates složek, zjistí .vstdir soubory, které nalezne. Soubor .vstdir je soubor XML, který řídí vzhled typ projektu v **nový projekt** dialogové okno. V souboru .vstdir použít \<LocalizedName > značky na název **typy projektů** uzlu.  
  
 Například soubor \CSharp\Database\TemplateIndex.vstdir obsahuje tuto značku:  
  
```  
<LocalizedName Package="{462b036f-7349-4835-9e21-bec60e989b9c}" ID="4598"/>  
```  
  
 Tato hodnota určuje satelitní knihovny DLL a prostředků ID lokalizované řetězce, který v tomto případě názvy kořenový uzel **databáze**. Lokalizovaný název může obsahovat speciální znaky, které nejsou k dispozici pro názvy složek, jako například **.NET**.  
  
 Pokud žádné \<LocalizedName > značky, typ projektu se ve složce samostatně, nazývá **SmartPhone2003**.  
  
##### <a name="finding-the-sort-order-for-a-project-type"></a>Hledání pořadí řazení typu projektu  
 K určení pořadí řazení typ projektu, použijte .vstdir soubory \<SortOrder > značky.  
  
 Například soubor \CSharp\Windows\Windows.vstdir obsahuje tuto značku:  
  
```  
<SortOrder>5</SortOrder>  
```  
  
 Soubor \CSharp\Database\TemplateIndex.vstdir má značku s hodnotou větší:  
  
```  
<SortOrder>5000</SortOrder>  
```  
  
 Čím nižší je číslo v \<SortOrder > značky, tím vyšší pozice ve stromu, proto **Windows** uzel se objeví vyšší než **databáze** uzel v **typy projektů**  stromu.  
  
 Pokud žádné \<SortOrder > Značka je zadán pro typ projektu, zobrazí se v abecedním pořadí následující všechny typy projektů, které obsahují \<SortOrder > specifikace.  
  
 Všimněte si, že nejsou žádné .vstdir soubory ve složce Dokumenty (**šablony**) složek. Názvy typů projektu aplikace uživatele nejsou lokalizovány a jsou v abecedním pořadí.  
  
#### <a name="a-quick-review"></a>Rychlá kontrola  
 Pojďme upravit **nový projekt** dialogové okno a vytvořte novou šablonu projektu uživatele.  
  
1.  Přidáte podsložku MyProjectNode do složky 14.0\Common7\IDE\ProjectTemplates\CSharp \Program Files\Microsoft Visual Studio.  
  
2.  Vytvořte soubor MyProject.vstdir ve složce MyProjectNode pomocí libovolného textového editoru.  
  
3.  Přidejte do souboru .vstdir tyto řádky:  
  
    ```  
    <TemplateDir Version="1.0.0">  
        <SortOrder>6</SortOrder>  
    </TemplateDir>  
    ```  
  
4.  Uložte a zavřete soubor .vstdir.  
  
5.  Vytvořte soubor MyProject.vstemplate ve složce MyProjectNode pomocí libovolného textového editoru.  
  
6.  Přidejte soubor .vstemplate tyto řádky:  
  
    ```  
    <VSTemplate Version="2.0.0" Type="Project" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <TemplateData>  
            <ProjectType>CSharp</ProjectType>  
        </TemplateData>  
    </VSTemplate>  
    ```  
  
7.  The.vstemplate soubor uložte a zavřete editor.  
  
8.  Odešlete soubor .vstemplate do nové složky komprimované MyProjectNode\MyProject.zip.  
  
9. Visual Studio příkazové okno zadejte:  
  
    ```  
    devenv /installvstemplates  
    ```  
  
 Otevřete Visual Studio.  
  
1.  Otevřete **nový projekt** dialogové okno pole a rozbalte **Visual C#** uzel projektu.  
  
 ![MyProjectNode](../../extensibility/internals/media/myprojectnode.png "MyProjectNode")  
  
 **MyProjectNode** se zobrazí jako podřízený uzel z Visual C# jenom v uzlu systému Windows.  
  
## <a name="see-also"></a>Viz také  
 [Nové generace projektu: Pod pokličkou, část 2](../../extensibility/internals/new-project-generation-under-the-hood-part-two.md)