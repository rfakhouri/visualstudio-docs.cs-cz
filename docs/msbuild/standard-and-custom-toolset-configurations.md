---
title: Konfigurace sady nástrojů Standardní a vlastní | Microsoft Docs
ms.custom: ''
ms.date: 01/31/2018
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, custom toolset configurations
- MSBuild, msbuild.exe.config
ms.assetid: 15a048c8-5ad3-448e-b6e9-e3c5d7147ed2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c38d7ba577beedce8651bb291700a6c071ee7b48
ms.sourcegitcommit: 498e39e89a89ad7bf9dcb0617424fff999b1c3b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/21/2018
ms.locfileid: "36303013"
---
# <a name="standard-and-custom-toolset-configurations"></a>Standardní a vlastní konfigurace sady nástrojů
Sada nástrojů MSBuild obsahuje odkazy na úlohy, cílů a nástroje, které můžete použít pro sestavení projektu aplikace. MSBuild zahrnuje standardní sada nástrojů, ale můžete také vytvořit vlastní modulové. Informace o tom, jak určit nástrojů najdete v tématu [sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md)  
  
## <a name="standard-toolset-configurations"></a>Konfigurace standardní sady nástrojů  
 MSBuild 15.0 zahrnuje následující standardní modulové:  
  
|Atribut ToolsVersion|Sada nástrojů cestu (jako je zadaný ve vlastnosti MSBuildToolsPath nebo MSBuildBinPath sestavení)|  
|------------------|--------------------------------------------------------------------------------------------|  
|2.0|*Cesta instalace systému Windows*\Microsoft.Net\Framework\v2.0.50727\|  
|3.5|*Cesta instalace systému Windows*\Microsoft.NET\Framework\v3.5\|  
|4.0|*Cesta instalace systému Windows*\Microsoft.NET\Framework\v4.0.30319\|  
|15.0|*Cesta instalace Visual Studio*\MSBuild\15.0\bin|  
  
 `ToolsVersion` Hodnota určuje, který je používán nástrojů projekt, který generuje Visual Studio. V aplikaci Visual Studio 2017, výchozí hodnota je "15.0" (bez ohledu na to jaké verze zadaná v souboru projektu), ale tento atribut lze přepsat pomocí **/toolsversion** přepnout na příkazovém řádku. Informace o tento atribut a dalších způsobů určení `ToolsVersion`, najdete v části [přepsání nastavení parametru ToolsVersion](../msbuild/overriding-toolsversion-settings.md).  
  
 Visual Studio 2017 nepoužívá klíč registru pro cestu k MSBuild. U verzí nástroje MSBuild před 15.0, které jsou nainstalované s Visual Studio 2017 zadejte následující klíče registru cestu instalace MSBuild.exe.  
  
|Klíč registru|Název klíče|Hodnotu řetězce klíčů|  
|------------------|--------------|----------------------|  
|\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ MSBuild\ToolsVersions\2.0\  |MSBuildToolsPath|Cesta instalace rozhraní .NET framework 2.0|  
|\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ MSBuild\ToolsVersions\3.5\  |MSBuildToolsPath|Cesta instalace rozhraní .NET framework 3.5|  
|\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ MSBuild\ToolsVersions\4.0\  |MSBuildToolsPath|Cesta instalace rozhraní .NET framework 4|  
  
### <a name="sub-toolsets"></a>Sub – modulové  
 Pokud klíč registru v předchozí tabulce obsahuje podklíč, MSBuild se používá k určení cestu dílčí nástrojů, který přepíše cestu, do sady nástrojů nadřazené. Následující podklíč je příklad:  
  
 \HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\ToolsVersions\12.0\12.0  
  
 Pokud se všechny vlastnosti jsou definovány v základní sada nástrojů a vybrané dílčí sada nástrojů, se používají definice vlastností v sady nástrojů sub. Sada nástrojů MSBuild 4.0 určují `SDK40ToolsPath` tak, aby odkazoval 7.0a SDK, ale MSBuild 4.0\11.0 nástrojů definuje stejnou vlastnost tak, aby odkazoval 8.0a SDK. Pokud `VisualStudioVersion` nenastavenou `SDK40ToolsPath` by mohlo ukazovat na 7.0a, ale pokud `VisualStudioVersion` je nastaven na 11.0, vlastnost byste místo toho přejděte na 8.0a.  
  
 `VisualStudioVersion` Sestavení vlastnost určuje, zda sada nástrojů dílčí stane aktivní. Například `VisualStudioVersion` hodnotu "12.0" Určuje dílčí-sada nástrojů MSBuild 12.0. Další informace najdete v tématu části dílčí modulové [sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md).  
  
> [!NOTE]
>  Doporučujeme vyhnout změna těchto nastavení. Nicméně můžete přidat vlastní nastavení a definovat vlastní sada nástrojů platná pro celý počítač definice podle popisu v další části.  
  
## <a name="custom-toolset-definitions"></a>Definice vlastní sada nástrojů  
 Když standardní sada nástrojů nesplňuje své požadavky na sestavení, můžete vytvořit vlastní sadu nástrojů. Například můžete mít scénáři testovacího prostředí sestavení, ve kterém musí mít samostatném systému za účelem vytváření [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projekty. Pomocí vlastních nástrojů můžete přiřadit vlastní hodnoty a `ToolsVersion` atributu při vytváření projektů nebo spustit MSBuild.exe. Tímto způsobem můžete také použít `$(MSBuildToolsPath)` vlastnost k importu .targets souborů z adresáře, jakož i definování vlastní vlastnosti vlastní sady nástrojů, které lze použít pro všechny projekt, který používá tento nástrojů.  
  
 Zadejte vlastní sady nástrojů v konfiguračním souboru pro MSBuild.exe (nebo pro vlastní nástroj, který je hostitelem nástroje MSBuild modul, pokud je to, co používáte). Konfiguračního souboru pro MSBuild.exe může obsahovat třeba následující definici sady nástrojů, pokud jste si přáli přepsat výchozí chování 15.0 parametru ToolsVersion.  
  
```xml  
<msbuildToolsets default="15.0">  
   <toolset toolsVersion="15.0">  
      <property name="MSBuildToolsPath"   
        value="C:\SpecialPath" />  
   </toolset>  
</msbuildToolsets>  
```  
  
 `<msbuildToolsets>` je také nutné definovat v konfiguračním souboru, následujícím způsobem.  
  
```xml  
<configSections>  
   <section name="msbuildToolsets"         
       Type="Microsoft.Build.BuildEngine.ToolsetConfigurationSection,   
       Microsoft.Build.Engine, Version=15.1.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a"  
   </section>  
</configSections>  
```  
  
> [!NOTE]
>  Čtení správně, `<configSections>` musí být první část v `<configuration>` oddílu.  
  
 `ToolsetConfigurationSection` je vlastní konfigurační oddíl, který lze použít pro vlastní konfigurace pomocí libovolného nástroje MSBuild hostitele. Pokud používáte vlastní sada nástrojů, hostitel nemá žádné akce k chybě při inicializaci modulu sestavení s tím rozdílem, poskytuje konfiguraci položek souboru. Definováním položky v registru můžete zadat celý počítač modulové, které se vztahují k MSBuild.exe, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]a všechny hostitele nástroje MSBuild.  
  
> [!NOTE]
>  Pokud konfigurační soubor systému definuje nastavení `ToolsVersion` který už je definovaný v registru, nejsou sloučit dva definice. Definice v konfiguračním souboru má přednost a nastavení v registru pro tento `ToolsVersion` jsou ignorovány.  
  
 Následující vlastnosti jsou specifické pro hodnotu `ToolsVersion` tedy používá v projektech:  
  
-   **$(MSBuildBinPath)** je nastaven na `ToolsPath` hodnotu, která je určená v registru nebo v konfiguračním souboru kde `ToolsVersion` je definována. `$(MSBuildToolsPath)` Nastavení v registru nebo konfiguračního souboru Určuje umístění klíčové úlohy a cíle. V souboru projektu to mapuje vlastnost $(MSBuildBinPath) a také vlastnost $(MSBuildToolsPath).  
  
-   `$(MSBuildToolsPath)` je vyhrazené vlastnost, která je zadána vlastností MSBuildToolsPath, který je uveden v konfiguračním souboru. (Tato vlastnost nahrazuje `$(MSBuildBinPath)`. Ale `$(MSBuildBinPath)` je přenesené z důvodu kompatibility.) Vlastní sada nástrojů musí definovat buď `$(MSBuildToolsPath)` nebo `$(MSBuildBinPath)` , ale ne pomocí obou, pokud oba mají stejnou hodnotu.  
  
 Můžete také přidat vlastní, specifické pro atribut ToolsVersion vlastnosti do konfiguračního souboru pomocí stejnou syntaxí, který použijete k přidání vlastnosti MSBuildToolsPath. Chcete-li zpřístupnit tyto vlastní vlastnosti souboru projektu, použijte stejný název jako název hodnoty, který je uveden v konfiguračním souboru. V konfiguračním souboru může definovat modulové však není modulové sub.  
  
## <a name="see-also"></a>Viz také  
 [Sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md)