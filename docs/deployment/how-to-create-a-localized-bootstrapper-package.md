---
title: 'Postupy: vytvoření lokalizovaného balíčku zaváděcího nástroje | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
helpviewer_keywords:
- localized bootstrapper packages
- dependencies, creating localized bootstrapper packages
- prerequisites, creating localized bootstrapper packages
ms.assetid: 66a1bc7e-6540-4164-963d-557196a69d8a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6948bd0a9cb3469141ea8c879effa130e7b00e86
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31566014"
---
# <a name="how-to-create-a-localized-bootstrapper-package"></a>Postupy: Vytvoření lokalizovaného balíčku zaváděcího nástroje
Po vytvoření balíčku zaváděcího nástroje lokalizované verze balíčku zaváděcího nástroje můžete vytvořit tak, že vytvoříte dva další soubory pro každé národní prostředí: softwarových licencí podmínky souboru (například eula.rtf) a manifestu balíčku (package.xml).  
  
 Ve výchozím nastavení zahrnuje sadu Visual Studio 2010 lokalizovaných balíčků zaváděcího nástroje pouze pro rozhraní .NET Framework 4, .NET Framework 4 Client Profile, 2.0 Runtime F # a 4.0 Runtime F #. Lokalizované balíčky lze vytvořit pro jiné samozaváděcích pomocí tří kroků.  
  
1.  Vytvořte složku s názvem za název národního prostředí v \Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\*BootstrapperPackageName*.  
  
2.  Vytvořte soubor, který obsahuje licenční podmínky softwaru pro balíček zaváděcího nástroje a vložte ho do nové složky.  
  
3.  Vytvoření manifestu balíčku s názvem package.xml, aktualizujte řetězce a jazykovou verzi a umístit soubor do nové složky. Pokud jste již vytvořili zaváděcího nástroje sady Visual Studio v jazyce cíl, můžete zkopírovat soubor package.xml Visual Studio a upravit ho v tomto kroku.  
  
> [!NOTE]
>  Pokud používáte projektu instalace k nasazení aplikací, je možné lokalizovat aplikace můžete změnit **lokalizace** vlastnost.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-localized-bootstrapper-package"></a>Chcete-li vytvořit lokalizovaného balíčku zaváděcího nástroje  
  
1.  Vytvořte složku s názvem za názvem národní prostředí.  
  
     Na 32bitové počítače, vytvořte složku v \Program Files\Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\\*BootstrapperPackageName*\ složky.  
  
     Na 64bitových počítačích, vytvořte složku v \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages soubory (86) \Program\\*BootstrapperPackageName*\ složky.  
  
     Následující tabulka uvádí názvy složek, které můžete použít tak, aby odpovídaly národního prostředí.  
  
    |Národní prostředí|Název složky|  
    |------------|-----------------|  
    |Čínština (zjednodušená)|zh-Hans|  
    |Čínština (tradiční)|zh-Hant|  
    |Čeština|cs|  
    |Němčina|Německo|  
    |Angličtina|en|  
    |Španělština|ES|  
    |Francouzština|FR|  
    |Italština|ho|  
    |Korejština|Ko|  
    |Japonština|Japonsko|  
    |Polština|PL|  
    |Portugalština (Brazílie)|pt-BR|  
    |Ruština|RU|  
    |Turečtina|tr|  
  
2.  Vytvořte soubor, který obsahuje licenční podmínky softwaru pro balíček zaváděcího nástroje a vložte ho do nové složky.  
  
3.  Vytvoření manifestu balíčku s názvem package.xml a vložte ho do nové složky. Další informace najdete v tématu [postupy: vytvoření balíčku Manifest](../deployment/how-to-create-a-package-manifest.md).  
  
4.  Aktualizace `<Strings>` části balíčku manifest tak, aby ve správném jazyce pro národní prostředí jsou řetězce.  
  
5.  Změna `<String Name="Culture">` hodnotu tak, aby odpovídaly název složky.  
  
6.  Uložte soubor package.xml.  
  
### <a name="to-create-a-bootstrapper-package-for-net-framework-35-service-pack-1-localized-in-french"></a>Chcete-li vytvořit balíček zaváděcího nástroje pro rozhraní .NET Framework 3.5 Service Pack 1 lokalizované ve francouzštině  
  
1.  Vytvořte složku s názvem fr. Název složky musí odpovídat názvu národního prostředí.  
  
     Na 32bitové počítače vytvořte složku ve složce SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\ \Program Files\Microsoft.  
  
     V 64bitových počítačích vytvořte složku ve složce \Program Files (86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\.  
  
2.  Umístěte do složky, fr lokalizované verzi licenční podmínky pro software.  
  
3.  Zkopírujte soubor \Program soubory (x86) \Microsoft SDKs\Windows\v7.0A\Bootstrapper\Packages\DotNetFX35SP1\en\package.xml ke složce fr a otevřete soubor v Návrháři XML.  
  
4.  Aktualizace `<Strings>` části balíčku manifest tak, aby řetězce chyby ve francouzštině.  
  
5.  Změna `<String Name="Culture">` hodnotu fr.  
  
6.  Uložte soubor package.xml.  
  
## <a name="see-also"></a>Viz také  
 [Vytváření balíčků zaváděcího nástroje](../deployment/creating-bootstrapper-packages.md)   
 [Požadavky na nasazení aplikací](../deployment/application-deployment-prerequisites.md)   
 [Postupy: Vytvoření manifestu balíčku](../deployment/how-to-create-a-package-manifest.md)