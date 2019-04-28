---
title: 'Postupy: Vytvoření lokalizovaného balíčku Bootstrapperu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
helpviewer_keywords:
- localized bootstrapper packages
- dependencies, creating localized bootstrapper packages
- prerequisites, creating localized bootstrapper packages
ms.assetid: 66a1bc7e-6540-4164-963d-557196a69d8a
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5ec3cd1365826c1a06b2d0f7bd6da377c8dc4d46
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440657"
---
# <a name="how-to-create-a-localized-bootstrapper-package"></a>Postupy: Vytvoření lokalizovaného balíčku Bootstrapperu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Po vytvoření balíčku zaváděcího nástroje lokalizované verze balíčku zaváděcího nástroje můžete vytvořit tak, že vytvoříte dva další soubory pro každé národní prostředí: software licenčních podmínek pro soubor (například eula.rtf) a manifestu balíčku (package.xml).  
  
 Ve výchozím nastavení, Visual Studio 2010 obsahuje lokalizované balíčky zaváděcího nástroje pouze pro rozhraní .NET Framework 4, .NET Framework 4 Client Profile, F# Runtime 2.0 a F# 4.0 modulu Runtime. Lokalizované balíčky pro jiné bootstrapperů můžete vytvořit pomocí tří kroků.  
  
1. Vytvořte složku s názvem za název národního prostředí v \Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\*BootstrapperPackageName*.  
  
2. Vytvořit soubor, který obsahuje licenční podmínky pro software pro balíček zaváděcího nástroje a vložit ho do nové složky.  
  
3. Vytvoření manifestu balíčku s názvem package.xml, aktualizujte řetězce a jazykovou verzi a vložit ho do nové složky. Pokud jste již vytvořili zaváděcí nástroj sady Visual Studio v cílovém jazyce, můžete zkopírovat souboru package.xml sady Visual Studio a upravit ho v tomto kroku.  
  
> [!NOTE]
> Pokud nasazení aplikace pomocí projektu instalace, je možné lokalizovat aplikaci tak, že změníte **lokalizace** vlastnost.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-localized-bootstrapper-package"></a>K vytvoření lokalizovaného balíčku bootstrapperu  
  
1. Vytvořte složku s názvem za název národního prostředí.  
  
     V 32bitových počítačích, vytvořte složku v \Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\*BootstrapperPackageName*\ složky.  
  
     Na 64bitových počítačích, vytvořit složku v souborech (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages \Program\\*BootstrapperPackageName*\ složky.  
  
     Následující tabulka uvádí názvy složek, které můžete použít tak, aby odpovídaly národní prostředí.  
  
    |Národní prostředí|Název složky|  
    |------------|-----------------|  
    |Čínština (zjednodušená)|zh-Hans|  
    |Čínština (tradiční)|zh-Hant|  
    |Čeština|cs|  
    |Němčina|de|  
    |Angličtina|en|  
    |Španělština|es|  
    |Francouzština|fr|  
    |Italština|it|  
    |Korejština|Ko|  
    |Japonština|Japonsko|  
    |Polština|pl|  
    |Portugalština (Brazílie)|pt-BR|  
    |Ruština|ru|  
    |Turečtina|tr|  
  
2. Vytvořit soubor, který obsahuje licenční podmínky pro software pro balíček zaváděcího nástroje a vložit ho do nové složky.  
  
3. Vytvoření manifestu balíčku s názvem package.xml a vložit ho do nové složky. Další informace najdete v tématu [jak: Vytvoření manifestu balíčku](../deployment/how-to-create-a-package-manifest.md).  
  
4. Aktualizace `<Strings>` část balíček manifestu tak, že jsou řetězce ve správném jazyce pro národní prostředí.  
  
5. Změnit `<String Name="Culture">` hodnotu tak, aby odpovídaly názvu složky.  
  
6. Uložení souboru package.xml.  
  
### <a name="to-create-a-bootstrapper-package-for-net-framework-35-service-pack-1-localized-in-french"></a>Vytvoření balíčku zaváděcího nástroje pro .NET Framework 3.5 Service Pack 1 lokalizované ve francouzštině  
  
1. Vytvořte složku s názvem fr. Název složky musí odpovídat názvu národního prostředí.  
  
     Na 32bitových počítačích vytvořte složku ve složce SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\ \Program Files\Microsoft.  
  
     Na 64bitových počítačích vytvořte složku ve složce \Program Files (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\.  
  
2. Umístěte do složky fr lokalizovanou verzi licenční podmínky pro software.  
  
3. Zkopírujte soubor \Program soubory (x86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\en\package.xml fr složky a otevřete ho v Návrháři XML.  
  
4. Aktualizace `<Strings>` část balíček manifestu tak, aby chybové řetězce ve francouzštině.  
  
5. Změnit `<String Name="Culture">` hodnota, která má fr.  
  
6. Uložení souboru package.xml.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření balíčků Bootstrapperu](../deployment/creating-bootstrapper-packages.md)   
 [Nezbytné součásti nasazení aplikace](../deployment/application-deployment-prerequisites.md)   
 [Postupy: Vytvoření manifestu balíčku](../deployment/how-to-create-a-package-manifest.md)
