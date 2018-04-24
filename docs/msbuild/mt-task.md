---
title: MT – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- VC.Project.VCManifestTool.ResourceOutputFileName
- VC.Project.VCManifestTool.SuppressDependencyElement
- VC.Project.VCManifestTool.ManifestFromManagedAssembly
- VC.Project.VCManifestTool.GenerateCategoryTags
- VC.Project.VCManifestTool.EnableDPIAwareness
- vc.task.mt
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBUILD (Visual C++), MT task
- MT task (MSBuild (Visual C++))
ms.assetid: bb94913c-1042-4968-9f08-b394518e899f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: da1cc8b65ac43e05c692d1fe7a5af4d8ea6fe381
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="mt-task"></a>MT – úloha
Zabalí nástroj Microsoft Manifest mt.exe. Další informace najdete v tématu "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **MT** úloh. Většina úloh parametry a několik sad parametrů, odpovídají možnosti příkazového řádku.  
  
> [!NOTE]
>  V dokumentaci mt.exe používá pomlčka (**-**) jako předpona pro možnosti příkazového řádku, ale v tomto tématu používá lomítko (**/**). Buď předpona je přijatelná.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**AdditionalManifestFiles**|Volitelné **řetězec []** parametr.<br /><br /> Určuje název jeden nebo více souborů manifestu.<br /><br /> Další informace najdete v tématu **/manifest** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**AdditionalOptions**|Volitelné **řetězec** parametr.<br /><br /> Seznam možností příkazového řádku. Například "*/option1 /option2 /option#*". Pomocí tohoto parametru lze zadat parametry příkazového řádku, které nejsou reprezentovány jakékoliv **MT** parametr úloh.<br /><br /> Další informace najdete v tématu "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**assemblyIdentity –**|Volitelné **řetězec** parametr.<br /><br /> Určuje hodnoty atributu **assemblyIdentity** element manifestu. Zadejte seznam s položkami oddělenými čárkou, kde je první součást hodnota `name` atribut, za nímž následuje jeden nebo více dvojic název hodnota, které mají formuláře,  *\<název atributu > = < attribute_value >*.<br /><br /> Další informace najdete v tématu **/identity** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**ComponentFileName**|Volitelné **řetězec** parametr.<br /><br /> Určuje název knihovny DLL, kterou máte v úmyslu vytvořit ze souborů .rgs nebo .tlb. Tento parametr je povinný, pokud zadáte **RegistrarScriptFile** nebo **TypeLibraryFile** MT parametry úlohy.<br /><br /> Další informace najdete v tématu **/dll** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**DependencyInformationFile**|Volitelné **řetězec** parametr.<br /><br /> Určuje soubor informace závislostí použít Visual Studio ke sledování informací o závislostech sestavení pro nástroj manifestu.|  
|**EmbedManifest**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, vloží souboru manifestu v sestavení. Pokud `false`, vytvoří jako samostatný soubor manifestu.|  
|**EnableDPIAwareness**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, přidá do manifestu informace, které označí aplikace jako rozlišením DPI. Zápis palec aplikace umožňuje uživatelské rozhraní vypadat dobře, konzistentně napříč celou řadu nastavení zobrazení vysokou hodnotou DPI.<br /><br /> Další informace najdete v tématu "Vysoké DPI" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**GenerateCatalogFiles**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, generuje soubory katalogu definice (CDF).<br /><br /> Další informace najdete v tématu **/makecdfs** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**GenerateCategoryTags**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, způsobí, že generování značek kategorie. Pokud tento parametr je `true`, **ManifestFromManagedAssemblyMT** musí být zadaná také parametr úloh.<br /><br /> Další informace najdete v tématu **/category** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**InputResourceManifests**|Volitelné **řetězec** parametr.<br /><br /> Vstup manifestu z prostředku typu RT_MANIFEST, který má zadaný identifikátor. Zadejte prostředek, formuláře, *\<soubor>[***;***[***#***]<ID_prostředku>]*, kde nepovinný `resource_id` parametr je číslo záporné, 16 bitů.<br /><br /> Pokud žádné `resource_id` je zadán, bude použita výchozí hodnota CREATEPROCESS_MANIFEST_RESOURCE (1).<br /><br /> Další informace najdete v tématu **/inputresource** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**ManifestFromManagedAssembly**|Volitelné **řetězec** parametr.<br /><br /> Generuje manifest ze zadané spravované sestavení.<br /><br /> Další informace najdete v tématu **/managedassemblyname** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**ManifestToIgnore**|Volitelné **řetězec** parametr.<br /><br /> (Nepoužívá.)|  
|**OutputManifestFile**|Volitelné **řetězec** parametr.<br /><br /> Určuje název manifestu výstup. Pokud je tento parametr vynechán a pouze jeden manifest pracuje na, že manifest se upravují na místě.<br /><br /> Další informace najdete v tématu **/out** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**OutputResourceManifests**|Volitelné **řetězec** parametr.<br /><br /> Výstup manifest prostředku typu RT_MANIFEST, který má zadaný identifikátor. Prostředek je ve formátu, *\<soubor>[***;***[***#***]<ID_prostředku>]*, kde nepovinný `resource_id` parametr je číslo záporné, 16 bitů.<br /><br /> Pokud žádné `resource_id` je zadán, bude použita výchozí hodnota CREATEPROCESS_MANIFEST_RESOURCE (1).<br /><br /> Další informace najdete v tématu **/outputresource** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**RegistrarScriptFile**|Volitelné **řetězec** parametr.<br /><br /> Určuje název souboru registrátora skript (.) bez registrace manifestu podpora modelu COM pomocí.<br /><br /> Další informace najdete v tématu **/rgs** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**ReplacementsFile**|Volitelné **řetězec** parametr.<br /><br /> Určuje soubor, který obsahuje hodnoty pro replaceable řetězce v souboru registrátora skript (.).<br /><br /> Další informace najdete v tématu **/replacements** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**ResourceOutputFileName**|Volitelné **řetězec** parametr.<br /><br /> Určuje prostředky výstupního souboru použitého pro vložení manifestu do výstupu projektu @.|  
|**Zdroje**|Volitelné `ITaskItem[]` parametr.<br /><br /> Určuje seznam manifestu zdrojové soubory, které jsou oddělené mezerami.<br /><br /> Další informace najdete v tématu **/manifest** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**SuppressDependencyElement**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, generuje manifest bez závislostí elementy. Pokud tento parametr je `true`, také určit **ManifestFromManagedAssemblyMT** parametr úloh.<br /><br /> Další informace najdete v tématu **/nodependency** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**SuppressStartupBanner**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, zabraňuje zobrazení číslo zprávy o autorských právech a verzi, po spuštění úlohy.<br /><br /> Další informace najdete v tématu **/nologo** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**TrackerLogDirectory**|Volitelné `String` parametr.<br /><br /> Určuje zprostředkující adresář, kde jsou uloženy protokoly sledování pro tuto úlohu.|  
|**TypeLibraryFile**|Volitelné **řetězec** parametr.<br /><br /> Určuje název typu soubor knihovny (.tlb). Pokud zadáte tento parametr, také určit **ComponentFileNameMT** parametr úloh.<br /><br /> Další informace najdete v tématu **/TLB** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
|**UpdateFileHashes**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, vypočítá hodnotu hash soubory v cestě určeného **UpdateFileHashesSearchPathMT** parametr úloh a pak aktualizuje hodnotu **hash** atribut **soubor** element manifestu pomocí vypočtená hodnota.<br /><br /> Další informace najdete v tématu **/hashupdate** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu. Viz také **UpdateFileHashesSearchPath** parametr v této tabulce.|  
|**UpdateFileHashesSearchPath**|Volitelné `String` parametr.<br /><br /> Určuje cestu k vyhledávání na při aktualizaci hodnoty hash souboru. Tento parametr použijete s **UpdateFileHashesMT** parametr úloh.<br /><br /> Další informace najdete v tématu **UpdateFileHashes** parametr v této tabulce.|  
|**VerboseOutput**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, zobrazí podrobné informace o ladění.<br /><br /> Další informace najdete v tématu **/ verbose** možnost "Mt.exe" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)