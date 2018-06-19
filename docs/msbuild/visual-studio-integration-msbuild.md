---
title: Integrace sady Visual Studio (MSBuild) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, reference resolution
- MSBuild, well-known target names
- MSBuild, hosting
- MSBuild, editing project files
- MSBuild, Visual Studio integration
- MSBuild, IntelliSense
- MSBuild, output groups
- MSBuild, in-process compilers
- MSBuild, design-time target execution
ms.assetid: 06cd6d7f-8dc1-4e49-8a72-cc9e331d7bca
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd9dd101508fc55ff6287af534ee57e53e95d4e8
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31575933"
---
# <a name="visual-studio-integration-msbuild"></a>Integrace sady Visual Studio (MSBuild)
Visual Studio hostitelů [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] k načtení a vytvoření spravované projekty. Protože [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] zodpovídá za projektu, téměř každý projekt v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] můžete v úspěšně použít formát [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]i v případě projektu byla vytvořena pomocí různých nástrojů a má vlastní sestavení proces.  
  
 Toto téma popisuje konkrétní aspektů [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]na [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] hostování, měli byste zvážit při přizpůsobení projektů a .TARGETS – soubory, které chcete načíst a sestavení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. To vám pomůže zajistěte, aby [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] funkce, jako jsou funkce IntelliSense a ladění pracovních pro váš vlastní projekt.  
  
 Informace o projekty C++ najdete v tématu [soubory projektu](/cpp/ide/project-files).  
  
## <a name="project-file-name-extensions"></a>Přípony názvů souborů projektu  
 MSBuild.exe rozpozná všechny příponu názvu souboru projektu odpovídající vzoru. * proj. Ale [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozpozná pouze podmnožinu tyto projektu přípony názvů souborů, které určují konkrétní jazyk projektu systém, který načte projektu. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nemá jazykově neutrální [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] na základě systému projektu.  
  
 Například [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] systému projektu načte .csproj soubory, ale [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nemůže načíst soubor .xxproj. Soubor projektu pro zdrojové soubory v libovolné jazyce musí používat stejnou příponu jako [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] nebo [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] soubory pro otevření v projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
## <a name="well-known-target-names"></a>Známé názvy cílů  
 Kliknutím **sestavení** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] výchozí cíl, budou spuštěny v projektu. Často je také s názvem Tento cíl `Build`. Výběr **znovu sestavit** nebo **Vyčistit** příkaz se pokusí spustit cíl se stejným názvem v projektu. Kliknutím na tlačítko **publikovat** provede cíl s názvem `PublishOnly` v projektu.  
  
## <a name="configurations-and-platforms"></a>Konfigurace a platformy  
 Konfigurace jsou reprezentována v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty podle vlastností seskupeny v rámci `PropertyGroup` elementu, který obsahuje `Condition` atribut. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Chcete-li vytvořit seznam platformy k zobrazení a konfigurace projektu vypadá na tyto podmínky. Tento seznam úspěšná extrakce, podmínky musí mít formát, který je podobný následujícímu:  
  
```  
Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' "  
Condition=" '$(Configuration)' == 'Release' "   
Condition=" '$(Something)|$(Configuration)|$(SomethingElse)' == 'xxx|Debug|yyy' "  
```  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Hledat v podmínky na `PropertyGroup`, `ItemGroup`, `Import`, vlastnost a elementy položky pro tento účel.  
  
## <a name="additional-build-actions"></a>Další akce sestavení  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Umožňuje změnit název položky typu souboru, do projektu s **akce sestavení** vlastnost [vlastnosti souboru](http://msdn.microsoft.com/en-us/013c4aed-08d6-4dce-a124-ca807ca08959) okno. `Compile`, `EmbeddedResource`, `Content`, a `None` názvy typů položek jsou vždy uvedeny v této nabídce společně s žádné jiné položky typu názvy už v projektu. Aby se žádné názvy typů vlastní položky jsou vždy k dispozici v této nabídce, můžete přidat názvy typ položky s názvem `AvailableItemName`. Například přidáním následující k souboru projektu bude přidáte vlastní typ `JScript` do této nabídky pro všechny projekty, které ho importovat:  
  
```xml  
<ItemGroup>  
    <AvailableItemName Include="JScript"/>  
</ItemGroup>  
```  
  
> [!NOTE]
>  Názvy typů některé položky jsou speciální k [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] , ale není uvedený v této rozevírací nabídce.  
  
## <a name="in-process-compilers"></a>Vnitroprocesové kompilátory  
 Pokud je to možné, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] se pokusí použít verzi v procesu [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] kompilátoru pro zvýšení výkonu. (Nevztahuje se na [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)].) Tento postup fungovat správně musí být splněny následující podmínky:  
  
-   V projektu na cílový, musí být úloha s názvem `Vbc` pro [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] projekty.  
  
-   `UseHostCompilerIfAvailable` Parametr úlohy musí být nastaven na hodnotu true.  
  
## <a name="design-time-intellisense"></a>Technologie IntelliSense v době návrhu  
 Chcete-li získat podporu technologie IntelliSense [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] před sestavení generoval výstupní sestavení, musí být splněny následující podmínky:  
  
-   Musí být cílem s názvem `Compile`.  
  
-   Buď `Compile` cíl nebo jeden z jeho závislých musí volat úlohu kompilátoru projektu, například `Csc` nebo `Vbc`.  
  
-   Buď `Compile` cíl nebo jeden z jeho závislých musí způsobit kompilátoru přijímat všechny potřebné parametry pro technologii IntelliSense, zejména všechny odkazy.  
  
-   Musí být splněny podmínky uvedené v části "Vnitroprocesové kompilátory".  
  
## <a name="building-solutions"></a>Sestavování řešení  
 V rámci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], soubor řešení a projektu řazení sestavení jsou řízeny [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sám sebe. Při sestavování řešení s msbuild.exe na příkazovém řádku [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] analyzuje soubor řešení a řadí sestavení projektu. V obou případech jsou jednotlivě integrované projektů v pořadí závislostí a není provázán odkazy na projekt na projekt. Naopak když jednotlivých projektů jsou vytvořené s nástroji msbuild.exe, je provázán odkazy na projekt na projekt.  
  
 Při sestavování uvnitř [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], vlastnost `$(BuildingInsideVisualStudio)` je nastaven na `true`. Tímto lze v souborech projektu nebo .targets způsobí sestavení chovat jinak.  
  
## <a name="displaying-properties-and-items"></a>Zobrazení vlastností a položek  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] rozpozná určité názvy a hodnoty vlastností. Například následující vlastnost v projektu způsobí **aplikace Windows** se objeví v **typ aplikace** pole **Návrhář projektu**.  
  
```xml  
<OutputType>WinExe</OutputType>  
```  
  
 Hodnota vlastnosti se dá upravit v **Návrhář projektu** a uložit v souboru projektu. -Li tato vlastnost zadána neplatná hodnota tak, že ručně upravíte, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] se zobrazit upozornění při načtení projektu a nahraďte neplatná hodnota výchozí hodnotu.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Jste srozuměni s tím výchozí hodnoty pro některé vlastnosti. Tyto vlastnosti nebude do souboru projektu jako trvalý, pokud mají jiné než výchozí hodnoty.  
  
 Vlastnosti s libovolné názvy nejsou zobrazeny v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Chcete-li změnit libovolné vlastnosti v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], musíte v editoru XML otevřete soubor projektu a upravit je ručně. Další informace najdete v tématu [úpravy souborů projektu v sadě Visual Studio](#BKMK_EditingProjects) později v tomto tématu.  
  
 Položky definované v projektu s názvy typů libovolné položky jsou ve výchozím nastavení zobrazí v Průzkumníku řešení v jejich uzlu projektu. Pokud chcete skrýt položku ze zobrazení, nastavte `Visible` metadata, aby `false`. Například následující položku v procesu sestavení se bude podílet, ale nezobrazí v Průzkumníku řešení.  
  
```xml  
<ItemGroup>  
    <IntermediateFile Include="cache.temp">  
        <Visible>false</Visible>  
    </IntermediateFile>  
</ItemGroup>  
```  
  
 Položky, které jsou deklarované v souborech, které jsou importovány do projektu se nezobrazují ve výchozím nastavení. Položky vytvořené během procesu sestavení se nikdy zobrazí v Průzkumníku řešení.  
  
## <a name="conditions-on-items-and-properties"></a>Podmínky pro položky a vlastnosti  
 Během vytváření sestavení jsou plně dodrženy všechny podmínky.  
  
 Při určování hodnoty vlastností zobrazíte vlastnosti, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] zvažuje závislé konfigurace jsou vyhodnocovány jinak než vlastnosti považuje konfigurace nezávislé. Pro vlastnosti považuje konfigurace závislé, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nastaví `Configuration` a `Platform` vlastnosti správně a dává pokyn [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] znovu vyhodnotit projektu. Pro vlastnosti považuje konfigurace nezávislé, že je neurčitou, jak se vyhodnotí podmínky.  
  
 Podmíněné výrazy na položky jsou vždy ignorovat pro účely rozhodování, zda má být položka zobrazena v Průzkumníku řešení.  
  
## <a name="debugging"></a>Ladění  
 Aby bylo možné najít a spustit výstup sestavení a připojit ladicí program, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] musí vlastnosti `OutputPath`, `AssemblyName`, a `OutputType` správně definované. Ladicí program se nepodaří připojit, pokud proces vytváření nezpůsobila kompilátoru generovat soubor .pdb.  
  
## <a name="design-time-target-execution"></a>Provádění cílů v době návrhu  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pokusí se provést cílů se některé názvy při jeho načtení projektu. Zahrnout tyto cíle `Compile`, `ResolveAssemblyReferences`, `ResolveCOMReferences`, `GetFrameworkPaths`, a `CopyRunEnvironmentFiles`. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Spustí těmito cíli tak, aby kompilátor jde inicializovat na poskytovat technologii IntelliSense, může být inicializována ladicího programu a odkazy zobrazí v Průzkumníku řešení může být vyřešen. Pokud nejsou k dispozici tyto cíle, projekt bude zatížení a sestavení správně, ale dojde v době návrhu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] nebude plně funkční.  
  
##  <a name="BKMK_EditingProjects"></a> Úpravy souborů projektu v sadě Visual Studio  
 Chcete-li upravit [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu přímo, můžete otevřít soubor projektu v editoru Visual Studio XML.  
  
#### <a name="to-unload-and-edit-a-project-file-in-visual-studio"></a>Uvolnění projektu a jeho úprava v sadě Visual Studio  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídky projektu a zvolte **uvolnit projekt**.  
  
     Projekt je označena **(není k dispozici)**.  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídky projektu není k dispozici a potom zvolte **upravit \<soubor projektu >**.  
  
     Soubor projektu se otevře v editoru XML sady Visual Studio.  
  
3.  Upravit, uložte a zavřete soubor projektu.  
  
4.  V **Průzkumníku řešení**, otevřete místní nabídky projektu není k dispozici a potom zvolte **znovu načíst projekt**.  
  
## <a name="intellisense-and-validation"></a>Technologie IntelliSense a ověřování  
 Pokud chcete upravit soubory projektu pomocí editoru XML, Funkce IntelliSense a ověřování vycházejí z [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] soubory schématu. Byly nainstalovány do mezipaměti schématu, která lze nalézt v  *\<Visual Studio Instalační adresář >* \Xml\Schemas\1033\MSBuild.  
  
 Základní [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] typy jsou definované v Microsoft.Build.Core.xsd a běžné typy používané [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] jsou definovány v Microsoft.Build.CommonTypes.xsd. Schémata přizpůsobit tak, aby měli funkce IntelliSense a ověřování pro názvy typů vlastní položky, vlastnosti a úloh, můžete upravit Microsoft.Build.xsd nebo vytvořit vlastní schéma, které obsahuje schémata CommonTypes nebo Core. Pokud vytvoříte vlastní schéma, budete muset nasměrovat XML editor najít pomocí **vlastnosti** okno.  
  
## <a name="editing-loaded-project-files"></a>Úpravy načtených souborů projektu  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] ukládá do mezipaměti obsah souborů projektu a soubory importovat pomocí souborů projektu. Pokud chcete upravit soubor načíst projekt [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] vás automaticky vyzve k načtení projektu tak, aby tyto změny začnou platit. Ale pokud chcete upravit soubor importovat pomocí načíst projekt, budou existovat bez opětovného načtení výzvy a je nutné uvolnit a znovu načíst projekt ručně provést změny vstoupí v platnost.  
  
## <a name="output-groups"></a>Skupiny výstupu  
 Několik cílů, které jsou definované v Microsoft.Common.targets mít názvy končící na `OutputGroups` nebo `OutputGroupDependencies`. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] volá tyto cíle, chcete-li získat konkrétní seznam výstupy projektu. Například `SatelliteDllsProjectOutputGroup` cíl vytvoří seznam všech satelitní sestavení vytvoří sestavení. Tyto skupiny výstupu jsou používány funkcí, jako je publikování, nasazení a odkazy na projekt na projekt. Načte a sestavení projektech, které je nedefinují [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ale některé funkce nemusí fungovat správně.  
  
## <a name="reference-resolution"></a>Překlad odkazů  
 Překlad odkazů je proces, pomocí položky odkaz uložené v souboru projektu zjistit skutečný sestavení. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] překlad odkazů, chcete-li zobrazit podrobné vlastnosti pro každý odkaz v musí aktivovat **vlastnosti** okno. Následující seznam popisuje tři typy odkazů a způsob jejich řešení.  
  
-   Odkazy na sestavení:  
  
     Systém projektu volá cíl s dobře známý název `ResolveAssemblyReferences`. Tento cíl by měl vytvořit položky s názvem typu položky `ReferencePath`. Každá z těchto položek by měl mít specifikace položky (hodnota `Include` atribut položky) obsahující úplnou cestu k odkazu. Položky musí mít všechny metadata ze vstupní položky předána kromě následující nové metadata:  
  
    -   `CopyLocal`, která určuje, zda je sestavení by se měl zkopírovat do výstupní složky nastavit na true nebo false.  
  
    -   `OriginalItemSpec`, obsahující specifikace původní položka odkazu.  
  
    -   `ResolvedFrom`, pokud byl vyřešen z nastavena na hodnotu "{TargetFrameworkDirectory}" [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] adresáře.  
  
-   COM odkazy:  
  
     Systém projektu volá cíl s dobře známý název `ResolveCOMReferences`. Tento cíl by měl vytvořit položky s názvem typu položky `ComReferenceWrappers`. Každá z těchto položek by měl mít specifikace položky obsahující úplnou cestu k sestavení vzájemné spolupráce pro odkaz na COM. Položky musí mít všechny metadata z metadat předaný prostřednictvím, kromě nového vstupní položky s názvem `CopyLocal`, která určuje, zda je sestavení by se měl zkopírovat do výstupní složky nastavit na true nebo false  
  
-   Nativní odkazy  
  
     Systém projektu volá cíl s dobře známý název `ResolveNativeReferences`. Tento cíl by měl vytvořit položky s názvem typu položky `NativeReferenceFile`. Položky musí mít všechny metadata ze vstupní položky předána, kromě nová metadat s názvem `OriginalItemSpec`, obsahující specifikace původní položka odkazu.  
  
## <a name="performance-shortcuts"></a>Zkrácení postupu pro zvýšení výkonu  
 Pokud spustíte ladění ve Visual Studiu (buď výběrem klávesy F5 nebo výběrem **ladění**, **spustit ladění** v řádku nabídek), procesu sestavení používá kontrolu rychlé aktualizace pro zlepšení výkonu. V některých případech, kde vytvořit vlastní sestavení soubory, které získat vytvořené zase kontrola rychlé aktualizace neidentifikuje správně změněné soubory. Projekty, které je třeba více důkladné kontroly aktualizací můžete vypnout Rychlá kontrola nastavením proměnné prostředí `DISABLEFASTUPTODATECHECK=1`. Alternativně projekty tento parametr můžete nastavit jako ve vlastnosti nástroje MSBuild v projektu nebo v souboru, který importuje projektu.  
  
 Pro regulární sestavení v sadě Visual Studio kontrola rychlé aktualizace netýká a projekt se sestavení, jako kdyby vyvolat sestavení na příkazovém řádku.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: rozšíření procesu sestavení sady Visual Studio](../msbuild/how-to-extend-the-visual-studio-build-process.md)   
 [Spuštění sestavení z prostředí IDE](../msbuild/starting-a-build-from-within-the-ide.md)   
 [Registrace rozšíření rozhraní .NET Framework](../msbuild/registering-extensions-of-the-dotnet-framework.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)   
 [Item – Element (MSBuild)](../msbuild/item-element-msbuild.md)   
 [Property – Element (MSBuild)](../msbuild/property-element-msbuild.md)   
 [Target – Element (MSBuild)](../msbuild/target-element-msbuild.md)   
 [CSC – úloha](../msbuild/csc-task.md)   
 [Vbc – úloha](../msbuild/vbc-task.md)