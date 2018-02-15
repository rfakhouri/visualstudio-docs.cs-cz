---
title: "Sada nástrojů MSBuild (atribut ToolsVersion) | Microsoft Docs"
ms.custom: 
ms.date: 01/31/2018
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, multitargeting
- targeting a specific .NET framework [MSBuild]
- MSBuild, targeting a specific .NET framework
- multitargeting [MSBuild]
ms.assetid: 40040ee7-4620-4043-a6d8-ccba921421d1
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: e274fa60ff209436be9d11f52464d7b42972ef47
ms.sourcegitcommit: f219ef323b8e1c9b61f2bfd4d3fad7e3d5fb3561
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/14/2018
---
# <a name="msbuild-toolset-toolsversion"></a>Sada nástrojů MSBuild (atribut ToolsVersion)
MSBuild používá sada nástrojů úlohy, cílů a nástrojů pro vytvoření aplikace. Sada nástrojů MSBuild obvykle zahrnuje microsoft.common.tasks souboru, soubor microsoft.common.targets a kompilátory například csc.exe a vbc.exe. Většina modulové lze použít pro kompilaci více než jedna verze rozhraní .NET Framework a více než jedné platformě systému. Sada nástrojů MSBuild 2.0 lze však cílí na rozhraní .NET Framework 2.0.  
  
## <a name="toolsversion-attribute"></a>ToolsVersion – atribut  
 Zadejte sady nástrojů v `ToolsVersion` atributu u [projektu](../msbuild/project-element-msbuild.md) element v souboru projektu. Následující příklad určuje, že projekt by měly být vytvořeny pomocí sady nástrojů MSBuild 15.0.  
  
```xml  
<Project ToolsVersion="15.0" ... </Project>  
``` 

> [!NOTE] 
> Některé projektu typy použijte `sdk` atribut místo `ToolsVersion`. Další informace najdete v tématu [balíčky, metadat a architektur](/dotnet/core/packages) a [doplňky csproj formátu pro .NET Core](/dotnet/core/tools/csproj).
  
## <a name="how-the-toolsversion-attribute-works"></a>Jak funguje ToolsVersion – atribut  
 Při vytvoření projektu v sadě Visual Studio nebo upgradovat existující projekt, atribut s názvem `ToolsVersion` je automaticky zahrnuty v projektu souboru a jeho hodnota odpovídá verzi nástroje MSBuild, který je součástí edicí sady Visual Studio. Další informace najdete v tématu [cílení na konkrétní verzi rozhraní .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md).  
  
 Když `ToolsVersion` hodnota je definována v souboru projektu, MSBuild používá tuto hodnotu k určení hodnoty vlastnosti sady nástrojů, které jsou k dispozici pro projekt. Jednu vlastnost nástrojů je `$(MSBuildToolsPath)`, která určuje cestu nástroje rozhraní .NET Framework. Pouze vlastnosti sady nástrojů (nebo `$(MSBuildBinPath)`), je vyžadován.  
  
 Spouštění v sadě Visual Studio 2013, sada nástrojů MSBuild verze je stejná jako číslo verze sady Visual Studio. Výchozí hodnota nástroje MSBuild je tato sada nástrojů v sadě Visual Studio a na příkazovém řádku, bez ohledu na verzi sady nástrojů v souboru projektu zadány.  Toto chování lze přepsat pomocí příznaku /ToolsVersion. Další informace najdete v tématu [přepsání nastavení parametru ToolsVersion](../msbuild/overriding-toolsversion-settings.md).  
  
 V následujícím příkladu MSBuild vyhledá soubor Microsoft.CSharp.targets pomocí `MSBuildToolsPath` vyhrazené vlastnost.  
  
```xml  
<Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />  
```  
  
 Můžete upravit hodnotu `MSBuildToolsPath` tak, že definujete vlastní sada nástrojů. Další informace najdete v tématu [standardní a vlastní konfigurace sady nástrojů](../msbuild/standard-and-custom-toolset-configurations.md)  
  
 Při vytvoření řešení na příkazovém řádku a zadejte `ToolsVersion` pro msbuild.exe, jsou vytvořeny všechny projekty a jejich závislosti projektu k projektu závislosti, `ToolsVersion`i v případě, že každý projekt v řešení určuje vlastní `ToolsVersion`. Chcete-li definovat `ToolsVersion` hodnotu na základě za projektu najdete v tématu [přepsání nastavení parametru ToolsVersion](../msbuild/overriding-toolsversion-settings.md).  
  
 `ToolsVersion` Atributu se taky používá pro migraci projektu. Například pokud otevřete Visual Studio 2008 projekt v sadě Visual Studio 2010, soubor projektu aktualizovaný obsahuje atribut ToolsVersion = "4.0". Pokud se pak pokusíte otevřít tohoto projektu v sadě Visual Studio 2008, nebudou rozpoznány upgradovaný `ToolsVersion` a proto sestavení projektu, jako kdyby byla atribut stále nastavena na 3.5.  
  
 Visual Studio 2010 a Visual Studio 2012 pomocí parametru ToolsVersion 4.0. Visual Studio 2013 používá atribut ToolsVersion z 12.0. Visual Studio 2015 používá atribut ToolsVersion 14.0 a Visual Studio 2017 15.0 parametru ToolsVersion. V mnoha případech můžete otevřít projekt v různých verzích sady Visual Studio bez úprav. Vždy používá správné sady nástrojů Visual Studio, ale budete informováni, pokud je verze použitá neodpovídá verzi v souboru projektu. Ve většině případů toto upozornění je neškodný, jako jsou kompatibilní ve většině případů modulové.  
  
 Sub – modulové, které jsou popsány dále v tomto tématu, povolí MSBuild automaticky přepnout na základě které sadu nástrojů použít v kontextu, ve kterém je spuštěn sestavení. Například MSBuild používá novější sadu nástrojů při spuštění v sadě Visual Studio 2012 než když ji spustí v sadě Visual Studio 2010, aniž byste museli výslovně změnit souboru projektu.  
  
## <a name="toolset-implementation"></a>Implementace sady nástrojů  
 Implementujte nástrojů výběrem cesty různé nástroje, cílů a úloh, které tvoří sada nástrojů. Nástroje v sady nástrojů, který definuje MSBuild pocházet z následujících zdrojů:  
  
-   Složka rozhraní .NET Framework.  
  
-   Další spravované nástroje.  
  
 Spravované nástroje patří ResGen.exe a TlbImp.exe.  
  
 MSBuild nabízí dva způsoby, jak získat přístup k sady nástrojů:  
  
-   Pomocí nástrojů vlastností  
  
-   Pomocí <xref:Microsoft.Build.Utilities.ToolLocationHelper> metody  
  
 Sada nástrojů Vlastnosti zadejte cesty nástroje. Od verze Visual Studio 2017, MSBuild už má pevnou umístění. Ve výchozím nastavení je umístěn ve složce MSBuild\15.0\Bin relativní k umístění instalace sady Visual Studio. V dřívějších verzích nástroje MSBuild používá hodnotu `ToolsVersion` atribut v souboru projektu najít odpovídající klíče registru a pak používá informace v klíči registru a nastavte vlastnosti sady nástrojů. Například pokud `ToolsVersion` má hodnotu `12.0`, pak MSBuild nastavuje vlastnosti sady nástrojů podle tohoto klíče registru: HKLM\Software\Microsoft\MSBuild\ToolsVersions\12.0.  
  
 Toto jsou vlastnosti nástrojů:  
  
-   `MSBuildToolsPath` Určuje cestu binárních souborů nástroje MSBuild.  
  
-   `SDK40ToolsPath` Určuje cestu dalších spravovaných nástrojů pro MSBuild 4.x (který může být 4.0 nebo 4.5).  
  
-   `SDK35ToolsPath` Určuje cestu dalších spravovaných nástrojů pro MSBuild 3.5.  
  
 Alternativně můžete určit sady nástrojů prostřednictvím kódu programu voláním metody <xref:Microsoft.Build.Utilities.ToolLocationHelper> třídy. Třída zahrnuje tyto metody:  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToDotNetFramework%2A> vrátí cestu složky pro rozhraní .NET Framework.  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToDotNetFrameworkFile%2A> vrátí cestu k souboru ve složce rozhraní .NET Framework.  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToDotNetFrameworkSdk%2A> vrátí cestu ke složce spravované nástroje.  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToDotNetFrameworkSdkFile%2A> vrátí cestu k souboru, která se obvykle nachází ve složce spravované nástroje.  
  
-   <xref:Microsoft.Build.Utilities.ToolLocationHelper.GetPathToBuildTools%2A> vrátí cestu nástroje pro sestavení.  
  
### <a name="sub-toolsets"></a>Sub – modulové  
 Verze nástroje MSBuild před 15.0 MSBuild používá klíč registru pro zadání cesty základní nástroje. Pokud klíč obsahuje podklíč, MSBuild se používá pro zadání cesty dílčí nástrojů, který obsahuje další nástroje. V takovém případě sada nástrojů je definována kombinací definice vlastností, které jsou definovány v oba klíče.  
  
> [!NOTE]
>  Pokud dojít ke konfliktu názvů vlastností sady nástrojů, hodnotu, která je definována pro podklíčů cestu přepíše hodnotu, která je definována pro kořenovou cestu klíče.  
  
 Sub modulové stane aktivní v přítomnosti z `VisualStudioVersion` vlastnost sestavení. Tato vlastnost může trvat jednu z těchto hodnot:  
  
-   "10.0" Určuje dílčí-sada nástrojů rozhraní .NET Framework 4  
  
-   "11.0" Určuje dílčí-sada nástrojů .NET Framework 4.5  
  
-   "12,0" Určuje dílčí-sada nástrojů .NET Framework 4.5.1 
  
 Sub – modulové 10.0 a 11.0 musí být použit s parametru ToolsVersion 4.0. V novějších verzích by měl odpovídat verzi dílčí nástrojů a parametru ToolsVersion.  
  
 Během vytváření sestavení, MSBuild automaticky určuje a nastavuje výchozí hodnotu pro `VisualStudioVersion` vlastnost, pokud je již definován.  
  
 MSBuild poskytuje přetížení pro `ToolLocationHelper` metody, které přidávají `VisualStudioVersion` uvedené hodnotu jako parametr  
  
 Sub – modulové byly zavedeny v rozhraní .NET Framework 4.5.  
  
## <a name="see-also"></a>Viz také  
 [Konfigurace standardní a vlastní sady nástrojů](../msbuild/standard-and-custom-toolset-configurations.md)   
 [Multitargeting](../msbuild/msbuild-multitargeting-overview.md)
