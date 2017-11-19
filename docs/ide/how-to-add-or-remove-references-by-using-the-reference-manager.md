---
title: "Postupy: Přidání nebo odebrání odkazů pomocí Správce odkazů | Microsoft Docs"
ms.custom: 
ms.date: 06/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.ReferenceManager
helpviewer_keywords:
- Visual C# projects, references
- references [Visual Studio], adding
- assemblies [Visual Studio], references
- Visual Basic projects, references
- project references, adding
- referencing components, adding references
- project references, removing
- referencing assemblies
- referencing components, removing references
- references [Visual Studio], removing
- referencing components, assemblies not listed
ms.assetid: 1aabb520-99b0-46c6-9368-21b4d84793eb
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3c5e414ab56641171e9d3f5cddf758b6a13a6458
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-add-or-remove-references-by-using-the-reference-manager"></a>Postupy: Přidání nebo odebrání odkazů pomocí správce odkazů
Můžete použít **správce odkazů** dialogové okno pro přidání a správa odkazuje součásti, které jste společnosti Microsoft, nebo vyvinuté jiné společnosti. Pokud vyvíjíte aplikace pro Universal Windows, projekt všechny správné knihoven DLL Windows SDK automaticky odkazuje. Pokud vyvíjíte aplikaci .NET, váš projekt odkazuje automaticky mscorlib.dll. Některé rozhraní API technologie .NET jsou zveřejněné v součásti, které budete muset přidat ručně. Odkazy na komponenty modelu COM nebo vlastní součásti nutné přidat ručně.  

## <a name="adding-and-removing-a-reference"></a>Přidání a odebrání odkazu  

#### <a name="to-add-a-reference"></a>Chcete-li přidat odkaz  

1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel odkazy a zvolte **přidat odkaz na**.  

2.  Zadejte odkazy na Přidat a potom vyberte **OK** tlačítko.  

 **Správce odkazů** k otevření a odkazy na dostupné skupinou. Typ projektu určuje, které z těchto skupin se zobrazí:  

-   Skupina Sestavení s podskupinami Rozhraní a Rozšíření  

-   Skupina Řešení s podskupinou Projekty  

-   Skupina Windows s podskupinami Jádro a Rozšíření. Odkazy ve Windows SDK nebo rozšíření sady SDK můžete prozkoumat pomocí **Prohlížeč objektů**.  

-   Skupina Procházení s podskupinou Nedávné  

## <a name="assemblies-tab"></a>Karta Sestavení  
 **Sestavení** karta Vypíše seznam všech sestavení rozhraní .NET Framework, které jsou k dispozici pro odkazování. **Sestavení** karta nemá seznam žádné sestavení z globální mezipaměti sestavení (GAC), protože sestavení v mezipaměti GAC jsou součástí běhové prostředí. Pokud nasazení nebo zkopírujte aplikaci, která obsahuje odkaz na sestavení, který je zaregistrován v mezipaměti GAC, nebude sestavení nasazené nebo zkopírovat s aplikací, bez ohledu na místní kopie nastavení. Další informace najdete v tématu [Správa odkazů v projektu](../ide/managing-references-in-a-project.md).  

 Pokud ručně přidáte odkaz na jakýkoli obor názvů EnvDTE (EnvDTE, EnvDTE80, EnvDTE90, EnvDTE90a nebo EnvDTE100), nastavte vlastnost Vložit typy spolupráce pro daný odkaz v okně Vlastnosti na hodnotu Nepravda. Nastavení této vlastnosti na hodnotu True může způsobit problémy sestavení z důvodu některé EnvDTE vlastnosti, která nelze vložit.  

 Všechny projekty určené pro klasickou plochu obsahují implicitní odkaz na knihovnu mscorlib. [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]projekty obsahují implicitní odkaz na Microsoft.VisualBasic. V [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], všechny projekty obsahují implicitní odkaz na System.Core i v případě, že se odebere ze seznamu odkazů.  

 Pokud typ projektu nepodporuje sestavení, na kartě se nebude zobrazovat na **správce odkazů** dialogové okno.  

 Karta Sestavení se skládá ze dvou dílčích karet:  

1.  Karta Rozhraní obsahuje všechna sestavení, která tvoří cílené rozhraní.  

    -   Inzerovaná sestavení se nacházejí v plné verzi rozhraní a jejich výčet je uveden v seznamu rozhraní, jestliže váš projekt cílí na profil cíleného rozhraní. Inzerovaná sestavení jsou zobrazena šedou barvou z důvodu odlišení od sestavení, která existují v cíleném profilu Rozhraní daného projektu. Pokud například projekt cílí na rozhraní .NET Framework 4 Client, seznam rozhraní obsahuje inzerovaná sestavení z rozhraní .NET Framework 4. Pokud uživatel přidá inzerovaný sestavení, uživatel je oznámení, která po **správce odkazů** se zavře dialogové, projekt bude možné změnit cíl na necílené rozhraní .NET Framework 4 a přidá se inzerovaný sestavení.  

    -   Projekty pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikace obsahovat odkazy na všechna sestavení v cílovou [!INCLUDE[net_win8_profile](../ide/includes/net_win8_profile_md.md)] ve výchozím nastavení při vytváření projektu. V projektech spravované, jen pro čtení uzlu ve složce odkazy v **Průzkumníku řešení** označuje odkaz na celý Framework. Podle toho, nebude kartě Framework výčet některý z těchto sestavení z rozhraní a místo toho zobrazí se následující zpráva: "všechna sestavení Framework se už neodkazuje. Použijte prohlížeč objektů a prozkoumejte odkazy v rozhraní Framework." Pro stolní projekty na kartě Framework vytvoří výčet sestavení z cílové rozhraní a uživatel musí přidat odkazy, které aplikace vyžaduje.  

2.  Karta Rozšíření obsahuje seznam všech sestavení, která vyvinuli externí dodavatelé součástí a ovládacích prvků za účelem rozšíření cíleného rozhraní. Podle účelu dané aplikace mohou být tato sestavení potřebná.  

    -   Karta Rozšíření zobrazuje výčet sestavení, která jsou zaregistrována v následujících umístěních:  

        ```  
        32-bit machine:  
        HKEY_CURRENT_USER\SOFTWARE\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]  
        HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]  
        64-bit machine:  
        HKEY_CURRENT_USER\SOFTWARE\Wow6432Node\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]  
        HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\[Target Framework Identifier]\v[Target Framework Version]\AssemblyFoldersEx\[UserComponentName]\@default=[Disk location of assemblies]  
        And older versions of the [Target Framework Identifier]  
        ```  

         Například pokud projektu cílem rozhraní .NET Framework 4 na počítač s 32bitovou, rozšíření se zobrazí seznam sestavení, které jsou zaregistrovány v rámci \Microsoft\\. NETFramework\v4.0\AssemblyFoldersEx\\, \Microsoft\\. NETFramework\v3.5\AssemblyFoldersEx\\, \Microsoft\\. NETFramework\v3.0\AssemblyFoldersEx\\a \Microsoft\\. NETFramework\v2.0\AssemblyFoldersEx\\.  

 Některé součásti v seznamu nemusí být zobrazeny, v závislosti na [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze vašeho projektu. Tato situace může nastat za následujících podmínek:  

-   Komponenta, která používá nejnovější verzi rozhraní .NET Framework je nekompatibilní s projektu, jehož cílem dřívější verzi rozhraní .NET Framework.  

     Informace o tom, jak změnit cílová verze rozhraní .NET Framework pro projekt najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).  

-   Komponenta, která používá [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] není kompatibilní s projektu, jehož cílem [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)].  

     Když vytvoříte novou aplikaci, některé cílové projekty [!INCLUDE[net_v45](../ide/includes/net_v45_md.md)] ve výchozím nastavení.  

-   Neměli byste přidávání odkazů na soubor do jiného projektu výstupy ve stejném řešení, protože to může způsobit chyby kompilace. Místo toho použijte **projekty** kartě **přidat odkaz na** dialogové okno vytvořit odkazy na projekt na projekt. To usnadňuje vývoj v týmu tím, že umožňuje lepší správu knihovny tříd, které vytvoříte ve vašich projektů. Další informace najdete v tématu [řešení potíží s odkazy na přerušený](../ide/troubleshooting-broken-references.md).  

-   > [!NOTE]
    >  V sadě Visual Studio 2015 nebo novější je vytvořen odkaz na soubor místo odkaz na projekt, pokud cílová verze rozhraní .NET Framework jeden projektu je verze 4.5 nebo novější, a cílovou verzi sady jiný projekt je verze 2, 3, 3.5 nebo 4.0.  

#### <a name="to-display-an-assembly-in-the-add-reference-dialog-box"></a>Chcete-li zobrazit v dialogovém okně Přidat odkaz na sestavení  

-   Přesuňte nebo zkopírujte sestavení do jednoho z následujících umístění:  

    -   Aktuální adresář projektu. (Tyto sestavení můžete najít pomocí **Procházet** karta.)  

    -   Další adresáře projektu ve stejném řešení. (Tyto sestavení můžete najít pomocí **projekty** karta.)  

     \-nebo –  

-   Nastavte klíč registru, který určuje umístění sestavení, které chcete zobrazit:  

     Pro 32bitový operační systém přidejte jedno z následujících klíčů registru.  

    -   [HKEY_CURRENT_USER\SOFTWARE\Microsoft\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"  

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"  

     Pro 64bitový operační systém přidejte jedno z těchto klíčů registru v podregistru 32bitového registru.  

    -   [HKEY_CURRENT_USER\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"  

    -   [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. NETFramework\\*VersionMinimum*\AssemblyFoldersEx\MyAssemblies]@= "*AssemblyLocation*"  

     *VersionMinimum* je nejnižší verze rozhraní .NET Framework, která se použije. Pokud *VersionMinimum* je v3.0, složky zadané v AssemblyFoldersEx vztahují na projekty cílených rozhraní .NET Framework 3.0 a novějších.  

     *AssemblyLocation* je sestavení, která se má zobrazit v adresáři **přidat odkaz na** dialogové okno, například C:\MyAssemblies\\.  

     Vytvoření klíče registru pod uzlem HKEY_LOCAL_MACHINE umožňuje všem uživatelům zobrazit sestavení v zadaném umístění v **přidat odkaz na** dialogové okno. Vytvoření klíče registru pod uzlem HKEY_CURRENT_USER ovlivní pouze nastavení pro aktuálního uživatele.  

     Otevřete **přidat odkaz na** dialogové okno znovu. Sestavení by se měla objevit na **.NET** kartě. Pokud ne, ujistěte se, že sestavení jsou umístěny v zadané *AssemblyLocation* adresáře, restartujte Visual Studio a akci opakujte.  

## <a name="com-tab"></a>Karta COM  
 Karta COM obsahuje seznam všech komponent COM, které jsou k dispozici pro odkazování. Pokud chcete přidat odkaz na registrovanou knihovnu DLL modelu COM, která obsahuje vnitřní manifest, nejprve zrušte registraci dané knihovny DLL. V opačném případě sada Visual Studio přidá odkaz na sestavení jako ovládací prvek ActiveX namísto jako nativní knihovnu DLL.  

 Pokud typ projektu nepodporuje COM, na kartě se nebude zobrazovat na **správce odkazů** dialogové okno.  

## <a name="solution-tab"></a>Karta Řešení  
 Na kartě Řešení jsou uvedeny všechny kompatibilní projekty v aktuálním řešení, a to na dílčí kartě Projekty.  

 Projekt může odkazovat na jiný projekt, který cílí na jinou verzi rozhraní .NET Framework. Například můžete vytvořit projektu s cílem [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] , ale který odkazuje na sestavení, které se sestavily pro rozhraní .NET Framework 2. Však nemůže odkazovat na rozhraní .NET Framework 2 projektu [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] projektu. Další informace najdete v tématu [cílení na konkrétní verzi rozhraní .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md).  

 Projektu, jehož cílem [!INCLUDE[net_v40_short](../code-quality/includes/net_v40_short_md.md)] není kompatibilní s projektu, jehož cílem [!INCLUDE[net_client_v40_long](../deployment/includes/net_client_v40_long_md.md)].  

 V [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], odkaz na soubor místo odkaz na projekt se vytvoří, pokud jeden projektu cílí na rozhraní .NET Framework 4 a jiného projektu zaměřuje na starší verzi.  

 Projektu, jehož cílem [!INCLUDE[net_win8_profile](../ide/includes/net_win8_profile_md.md)] nelze přidat odkaz na projekt do projektu, jehož cílem naopak rozhraní .NET Framework a naopak.  

## <a name="windows-tab"></a>Karta Windows  
 Karta Windows obsahuje všechny sady SDK, které jsou specifické pro platformy, na kterých běží operační systém Windows.  

 Soubor WinMD je možné v sadě Visual Studio vygenerovat dvěma způsoby:  

-   **[!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]aplikace spravované projekty**: [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] projekty aplikací můžete výstup WinMD binárních souborů nastavením vlastnosti projektu &#124; Výstupní typ = souboru WinMD. Název souboru WinMD musí představovat nadřazený obor názvů všech oborů názvů, které existují jeho v rámci. Pokud například projekt obsahuje obory názvů A.B a A.B.C, možné názvy pro soubory WinMD na jeho výstupu jsou A.winmd a A.B.winmd. Pokud uživatel zadá vlastnosti projektu &#124; Název sestavení nebo vlastnosti projektu &#124; Namespace hodnotu, která je nesouvislý ze sady obory názvů v projektu nebo je nadmnožinou obor názvů v rámci projektu, se generuje upozornění sestavení: 'A.winmd' není platný .winmd název souboru pro toto sestavení. Všechny typy v rámci souboru metadat systému Windows musejí existovat v podřízeném oboru názvů daného názvu souboru. Typy, které nejsou v oboru názvů sub názvu souboru, nebudete moci být umístěné za běhu. V tomto sestavení je nejmenší společný obor názvů CSWSClassLibrary1“. Plochy projektu jazyka Visual Basic a Visual C# můžete využívat pouze WinMDs, který je vytvořen pomocí [!INCLUDE[win8](../debugger/includes/win8_md.md)] sady SDK, které se označují jako první strany WinMDs a WinMDs nelze vygenerovat.  

-   **[!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]Nativní projekty aplikací**: nativní WinMD soubor obsahuje pouze metadata. Jeho implementace se nachází v samostatném souboru knihovny DLL. Jeden může vytvářet nativní binární soubory výběrem šablony projektu komponenty prostředí Windows Runtime **nový projekt** dialogové okno nebo spuštěním z prázdného projektu a změna vlastností projektu pro generování souboru WinMD. Pokud projekt obsahuje nesouvislé obory názvů, chyba sestavení oznámí uživateli, aby sloučit své obory názvů nebo spustit nástroj MSMerge.  

 Karta Windows se skládá ze dvou podskupin.  

### <a name="core-subgroup"></a>Podskupina Jádro  
 Podskupina Jádro obsahuje seznam všech souborů WinMD (pro elementy prostředí Windows Runtime) v sadě SDK pro cílenou verzi systému Windows.  

 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)]projekty aplikace obsahovat odkazy na všechny WinMDs v [!INCLUDE[win8](../debugger/includes/win8_md.md)] SDK ve výchozím nastavení při vytváření projektu. V projektech spravované, jen pro čtení uzlu ve složce odkazy v **Průzkumníku řešení** označuje odkaz na celý [!INCLUDE[win8](../debugger/includes/win8_md.md)] SDK. Základní podskupinu v správce odkazů odpovídajícím způsobem, nebude výčet některý z těchto sestavení z [!INCLUDE[win8](../debugger/includes/win8_md.md)] SDK a místo toho zobrazí zpráva: "sady Windows SDK je již odkazovat. Použijte prohlížeč objektů a prozkoumejte odkazy v sadě Windows SDK."  

 V běžných projektů podskupinu základní nezobrazí ve výchozím nastavení. Prostředí Windows Runtime můžete přidat tak, že otevřete místní nabídce uzlu projektu výběr **uvolnit projekt**, přidání následující fragment kódu a opakovaným otevřením projektu (na uzel projektu zvolte **znovu načíst projekt**). Při vyvolání **správce odkazů** se zobrazí dialogové okno, podskupinu jádra.  

```  
<PropertyGroup>  
  <TargetPlatformVersion>8.0</TargetPlatformVersion>  
</PropertyGroup>  
```  

 Je nutné vybrat **Windows** v tato podskupina zaškrtávací políčko. Poté budete moci používat elementy prostředí Windows Runtime. Je také vhodné přidat System.Runtime, ve kterém Windows Runtime definuje některé standardní třídy a rozhraní, například rozhraní IEnumerable, které se používají v knihovnách prostředí Windows Runtime. Informace o tom, jak přidat System.Runtime najdete v tématu [spravované aplikace klasické pracovní plochy a prostředí Windows Runtime](http://msdn.microsoft.com/library/windows/apps/jj856306.aspx#consuming_standard_windows_runtime_types).  

### <a name="extensions-subgroup"></a>Podskupina Rozšíření  
 Podskupina Rozšíření obsahuje seznam uživatelských sad SDK, které rozšiřují cílenou platformu Windows. Na této kartě se zobrazí pro [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] aplikaci pouze projekty. Proto potřebují pouze první strany .winmd soubory nezobrazí běžných projektů na této kartě.  

 Sada SDK je kolekce souborů, které sada Visual Studio považuje za jedinou součást. Na kartě rozšíření sady SDK, které platí pro projekt, ze kterých **správce odkazů** byl vyvolán dialogové okno jsou uvedeny jako položky jednou. Při přidání do projektu, veškerý obsah sady SDK je spotřebovávají Visual Studio tak, aby uživatel nemusí provádět žádné další akce využívat obsah sady SDK technologie IntelliSense, sada nástrojů, návrháře, prohlížeč objektů, sestavení, nasazení, ladění a zabalení. Informace o tom, jak zobrazit vaše SDK na kartě rozšíření najdete v tématu [vytváření Software Development Kit](../extensibility/creating-a-software-development-kit.md).  

> [!NOTE]
>  Pokud projekt odkazuje na sadu SDK, které závisí na jiné sady SDK, Visual Studio nebude využívat druhý SDK, pokud uživatel ručně přidá odkaz na druhý SDK. Když uživatel vybere sadu SDK na **rozšíření** kartě **správce odkazů** uživateli identifikovat SDK závislosti tak, že uvedete nejen název a verzi sady SDK, ale také název žádné SDK pomáhá dialogové okno závislosti v podokně podrobností. Pokud je uživatel nebude Všimněte si, závislosti a přidá jenom SDK, MSBuild vyzve uživatele, přidání závislosti.  

 Pokud typ projektu nepodporuje **rozšíření**, na kartě se nezobrazí v **správce odkazů** dialogové okno.  

## <a name="browse-button"></a>Tlačítko Procházet  
 Můžete použít **Procházet** tlačítko procházení pro součást v systému souborů.  

 Projekt se může odkazovat na součást, která cílí na jinou verzi rozhraní .NET Framework. Můžete například vytvořit aplikaci, která cílí na rozhraní .NET Framework 4 Client Profile, jež odkazuje na součást, která cílí na rozhraní .NET Framework 2. Další informace najdete v tématu [cílení na konkrétní verzi rozhraní .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md).  

 Měli byste se vyhnout přidávání odkazů na soubory do výstupů jiného projektu ve stejném řešení, protože to může vést k chybám při kompilaci. Místo toho použijte **řešení** kartě **správce odkazů** dialogové okno vytvořit odkazy na projekt na projekt. Tento postup usnadňuje vývoj v týmu, neboť umožňuje lepší správu knihoven tříd, které vytvoříte ve svých projektech. Další informace najdete v tématu [řešení potíží s odkazy na přerušený](../ide/troubleshooting-broken-references.md).  

 Nelze procházet sadě SDK a přidejte do projektu. Je možné přejít pouze k souboru (například sestavení nebo souboru .winmd) a přidat jej do projektu.  

 Při provádění odkaz na sestavení souboru WinMD, očekávané rozložení je, že *FileName*.winmd, *FileName*.dll, a *FileName*.pri soubory jsou umístěny vedle sebe navzájem. Pokud odkazujete na soubor WinMD v následujících scénářích, do výstupního adresáře projektu budou zkopírovány neúplné sady souborů a v důsledku toho dojde k chybám při sestavení a za běhu.  

-   **Nativní součást**: k nativnímu projektu vytvoří jeden WinMD pro každý nesouvislé Sada oborů názvů a jednu knihovnu DLL, která se skládá z implementace. Soubory WinMDs budou mít nesouvislé názvy. Při odkazování na tento soubor nativní součásti, nástroje MSBuild nerozpozná, dissimilarly pojmenované WinMDs vytvořili jednu součást. V důsledku toho pouze stejně jako s názvem *FileName*.dll a *FileName*.winmd se zkopírují a dojde k chybám za běhu. Chcete-li tento problém vyřešit, vytvořte rozšiřující sadu SDK. Další informace najdete v tématu [vytváření Software Development Kit](../extensibility/creating-a-software-development-kit.md).  

-   **Použití ovládacích prvků**: minimálně ovládacího prvku XAML se skládá z *FileName*.winmd, *FileName*.dll, *FileName*.pri, *XamlName* XAML a *ImageName*.jpg. Při sestavení projektu, soubory prostředků, které jsou spojeny s odkazem na soubor nezískáte zkopírovaný do výstupního adresáře projektu a to pouze *FileName*.winmd, *FileName*.dll a *FileName*.pri budou zkopírovány. Chyby sestavení přihlášen uživatel informován o který prostředky *XamlName*XAML a *ImageName*.jpg chybí. Aby sestavení proběhlo úspěšně, bude uživatel muset ručně zkopírovat tyto soubory prostředků do výstupního adresáře projektu pro sestavení a ladění/dobu běhu. Chcete-li tento problém obejít, buď vytvořit Extension SDK podle kroků v [vytváření Software Development Kit](../extensibility/creating-a-software-development-kit.md) nebo upravit projektu souboru přidejte následující vlastnost:  

    ```  
    <PropertyGroup>  
    <GenerateLibraryOutput>True</GenerateLibraryOutput>  
    </PropertyGroup>  
    ```  

    > [!NOTE]
    >  Pokud tuto vlastnost přidáte, může být sestavení pomalejší.  

## <a name="recent"></a>Nedávné  
 Kartu Nedávné podporují karty Sestavení, COM, Windows a Procházet. Tato karta obsahuje seznam součástí, které byly v poslední době přidány do projektu.  

## <a name="search"></a>Hledat  
 V řádku hledání **správce odkazů** dialogové okno funguje přes kartu, která je aktivní. Například, pokud uživatel zadá "Systém" v panelu vyhledávání při **řešení** karta je aktivní, hledání nevrátí žádné výsledky, pokud řešení se skládá z název projektu, který obsahuje "Systém".  

## <a name="see-also"></a>Viz také  
 [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)
