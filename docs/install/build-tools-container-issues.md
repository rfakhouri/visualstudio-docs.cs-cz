---
title: Známé problémy pro kontejnery | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
ms.assetid: 140083f1-05bc-4014-949e-fb5802397c7a
author: heaths
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c433716b0a5623fa9b4f098952b4c951d8b52e12
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2018
---
# <a name="known-issues-for-containers"></a>Známé problémy pro kontejnery

Při instalaci sady Visual Studio na kontejner Docker se několik problémů.

## <a name="windows-container"></a>Kontejneru systému Windows

Následující známé problémy při instalaci Visual Studio sestavení 2017 nástroje do kontejneru systému Windows.

* Visual Studio nelze nainstalovat do kontejneru podle microsoft/windowsservercore:10.0.14393.1593 bitové kopie. Bitové kopie, které jsou označené verze Windows starší nebo novější by měla fungovat.
* Verze sady Windows SDK, které jsou starší než 10.0.14393 nelze nainstalovat. Některé balíčky se nepodaří nainstalovat a procesy, které závisí na těchto balíčků nebude fungovat.
* Je nutné předat `-m 2GB` (nebo více) při sestavování bitovou kopii. Některé úlohy vyžadují více paměti, než je výchozí hodnota 1 GB při instalaci.
* Je nutné nakonfigurovat Docker použít disky, které jsou větší než výchozích 20 GB.
* Je nutné předat `--norestart` na příkazovém řádku. Jak z psaní tohoto textu pokus o restartování Windows kontejneru uvnitř kontejneru vrátí `ERROR_TOO_MANY_OPEN_FILES` k hostiteli.

## <a name="build-tools-container"></a>Kontejner nástroje pro sestavení

Při použití nástroje sestavení kontejneru, může dojít k následující známé problémy. Zobrazte, zda opravy nebo pokud existují dalších známých problémech, navštivte https://developercommunity.visualstudio.com.

* IntelliTrace, nemusí fungovat [některé scénáře](https://github.com/Microsoft/vstest/issues/940) do kontejneru.

## <a name="get-support"></a>Získat podporu
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:
* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi.
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio).  (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také

* [Instalace Build Tools do kontejneru](build-tools-container.md)
* [Rozšířený příklad pro kontejnery](advanced-build-tools-container.md)
* [ID úlohy a součást Visual Studio 2017 nástroje pro sestavení](workload-component-id-vs-build-tools.md)
