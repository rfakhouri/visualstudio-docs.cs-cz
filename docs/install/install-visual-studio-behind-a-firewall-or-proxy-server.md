---
title: "Instalaci sady Visual Studio za serverem brány firewall nebo proxy server | Microsoft Docs"
description: 
ms.custom: 
ms.date: 08/01/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs
ms.assetid: 
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 3862c6ed49e00ffa3800cccbedb2b846823418ed
ms.sourcegitcommit: 06cdc1651aa7f45e03d260080da5a623d6258661
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2018
---
# <a name="install-visual-studio-behind-a-firewall-or-proxy-server"></a>Instalaci sady Visual Studio za serverem brány firewall nebo proxy server

Instalační program Visual Studio stáhne soubory z různých domén a jejich stahování serverů. Tato stránka obsahuje seznam adres URL domény, které můžete chtít "povolených" jako důvěryhodný ve skriptech nasazení.

Pokud je možné pro vaše prostředí, zvažte přidání následujících domén s protokoly HTTP a HTTPS.

## <a name="microsoft-domains"></a>Microsoft domains
| Domain | Účel |
| ------ | ------- |
| go.microsoft.com | Překlad adresy URL instalace |
| aka.ms | Překlad adresy URL instalace |
| download.visualstudio.microsoft.com | Nastavení umístění stahování balíčků |
| download.microsoft.com | Nastavení umístění stahování balíčků |
| download.visualstudio.com | Nastavení umístění stahování balíčků |
| dl.xamarin.com | Nastavení umístění stahování balíčků |
| visualstudiogallery.msdn.microsoft.com | Umístění souboru ke stažení rozšíření Visual Studia |
| www.visualstudio.com | Umístění dokumentace |
| docs.microsoft.com | Umístění dokumentace |
| msdn.microsoft.com | Umístění dokumentace |
| www.microsoft.com | Umístění dokumentace |
| *.windows.net | Přihlášení |
| *.microsoftonline.com | Přihlášení |
| *.live.com | Přihlášení |


## <a name="non-microsoft-domains"></a>Non-Microsoft domains
| Domain | Nainstaluje tyto úlohy |
| ------ | ------- |
| archive.apache.org |  Mobilní vývoj pomocí jazyka JavaScript <br />(Cordova) |
| cocos2d-x.org | Vývoj her s C++ <br />(Kokosové) |
| download.epicgames.com | Vývoj her s C++ <br />(Unreal Engine) |
| download.oracle.com | Mobilní vývoj pomocí jazyka JavaScript <br />(Java SDK) <br /><br />Mobilní vývoj pomocí rozhraní .NET <br />(Java SDK) |
| download.unity3d.com | Vývoj her s Unity <br />(Unity) |
| netstorage.unity3d.com | Vývoj her s Unity <br /> (Unity) |
| dl.google.com | Mobilní vývoj pomocí jazyka JavaScript <br />(Android SDK a NDK emulátoru) <br /><br />Mobilní vývoj pomocí rozhraní .NET <br />(Android SDK a NDK emulátoru) |
| www.incredibuild.com | Vývoj her s C++ <br />(IncrediBuild) |
| incredibuildvs2017i.azureedge.net | Vývoj her s C++ <br />(IncrediBuild) |
| www.python.org | Vývoj Python <br />(Python) <br /><br />Aplikace pro datové vědy a analýzy <br />(Python) |

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také
* [Nainstalovat Visual Studio 2017](install-visual-studio.md)
* [Nainstalujte Visual Studio 2017 pomocí parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md)
  * [Příklady parametrů příkazového řádku](command-line-parameter-examples.md)
  * [Referenční dokumentace úlohy a ID součásti](workload-and-component-ids.md)
* [Vytvoření instalace Visual Studio 2017 založené na síti](create-a-network-installation-of-visual-studio.md)
  * [Instalace certifikátů vyžadovaných pro instalaci offline sady Visual Studio](install-certificates-for-visual-studio-offline.md)
* [Automatizace instalace sady Visual Studio souborem odpovědí](automated-installation-with-response-file.md)
* [Automatické použití kódů Product Key při nasazení sady Visual Studio](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Nastavit výchozí hodnoty pro podnikové nasazení Visual Studio 2017](set-defaults-for-enterprise-deployments.md)
* [Zakázání nebo přesunutí mezipaměti balíčku](disable-or-move-the-package-cache.md)
* [Aktualizace založené na síti instalace sady Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Ovládací prvek aktualizace Visual Studio 2017 nasazení](controlling-updates-to-visual-studio-deployments.md)
* [Nástroje pro zjišťování a správu instancí sady Visual Studio](tools-for-managing-visual-studio-instances.md)
