---
title: Co&#39;nového v MSBuild 12.0 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9976a6ad-c052-4017-b848-35b5ae4a2f66
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d91ec9044461cf57bba8bb36a0d2e029635155c5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674914"
---
# <a name="what39s-new-in-msbuild-120"></a>Co&#39;nového v MSBuild 12.0
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [dokumentace k sadě Visual Studio 2017](https://docs.microsoft.com/visualstudio/).  
  
Nástroj MSBuild je nyní nainstalován jako součást sady Visual Studio, nikoli jako součást rozhraní .NET Framework. Aktuální číslo verze nástroje MSBuild je 12.0. Pokud chcete nainstalovat nástroj MSBuild samostatně, stáhněte si instalační balíček z [MSBuild Stáhnout](http://go.microsoft.com/fwlink/?LinkId=309745).  
  
## <a name="changed-path"></a>Změněné cesta  
 Nástroj MSBuild je nyní nainstalován přímo pod *% ProgramFiles %*– například v C:\Program Files\MSBuild\\.  
  
## <a name="changed-properties"></a>Změněné vlastnosti  
 V důsledku nové číslo verze se mění následující vlastnosti nástroje MSBuild:  
  
-   `MSBuildToolsVersion` pro tuto verzi sady nástrojů je 12.0.  
  
-   `MSBuildToolsPath` je teď %ProgramFiles%\MSBuild\12.0\bin na 32bitové operační systémy nebo %ProgramFiles%\MSBuild\12.0\bin\amd64 v 64bitových operačních systémech.  
  
-   `ToolsVersion` hodnoty můžete najít v HKLM\SOFTWARE\Microsoft\MSBuild\ToolsVersions\12.0 pro 32bitové operační systémy nebo HKLM\SOFTWARE\Wow6432Node\Microsoft\MSBuild\ToolsVersions\12.0 pro 64bitové operační systémy.  
  
-   `SDK35ToolsPath` a `SDK40ToolsPath` vlastnosti odkazovat na rozhraní .NET Framework SDK je zabalený s touto verzí sady Visual Studio (například 8.1a pro nástroje 4.X).  
  
## <a name="new-properties"></a>Nové vlastnosti  
  
-   `MSBuildFrameworkToolsPath` je nová vlastnost, která má hodnotu %windir%\Microsoft.NET\Framework\v4.0.30319 na 32bitové operační systémy nebo %windir%\Microsoft.NET\Framework64\v4.0.30319 v 64bitových operačních systémech. Toto je náhradou za `MSBuildToolsPath` , který je možné odkazovat na rozhraní .NET Framework nástroje a pomůcky.  
  
-   `MSBuildToolsPath` a `MSBuildFrameworkToolsPath` 32-bit ekvivalenty –`MSBuildToolsPath32` a `MSBuildFrameworkToolsPath32`–, který vždy odkazovalo na umístění, 32 bitů, bez ohledu na to, jestli je 32bitová nebo 64bitová verze nástroje MSBuild používá.

## <a name="see-also"></a>Viz také
[MSBuild](msbuild.md)


