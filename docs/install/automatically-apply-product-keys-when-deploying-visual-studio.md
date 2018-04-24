---
title: Automatické použití kódů product key při nasazení sady Visual Studio
description: Naučte se prostřednictvím kódu programu použití kódů product key při nasazení sady Visual Studio.
ms.date: 08/14/2017
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 122fbaa30b90eb7cb5f7cb5de210e86155573833
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>Automatické použití kódů product key při nasazení sady Visual Studio

Můžete použít kód product key prostřednictvím kódu programu jako součást skript, který slouží k automatizaci nasazení sady Visual Studio. Můžete nastavit kód product key na zařízení prostřednictvím kódu programu buď při instalaci sady Visual Studio nebo po dokončení instalace.

## <a name="apply-the-license-after-installation"></a>Použít licence, které jsou po instalaci

 Nainstalovaná verze sady Visual Studio s kódem product key můžete aktivovat pomocí `StorePID.exe` nástroj na cílových počítačích, v bezobslužném režimu. `StorePID.exe` je nástroj pro program, který se instaluje s Visual Studio 2017 v následujícím výchozím umístění: <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

 Spustit `StorePID.exe` se zvýšenými oprávněními, buď pomocí agenta System Center nebo příkazového řádku se zvýšenými oprávněními. Po ní následuje kód product key a kód produktu Microsoft (MPC).

>[!IMPORTANT]
> Nezapomeňte zahrnout pomlček kód product key.

 ```cmd
 StorePID.exe [product key including the dashes] [MPC]
 ```

 Následující příklad ukazuje příkazového řádku pro použití s licencí pro Visual Studio Enterprise 2017, který má MPC 08860, kód product key z `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`a předpokládá výchozí umístění instalace:

 ```cmd
 "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 08860
 ```

 V následující tabulce jsou uvedeny kódy MPC pro každý edice sady Visual Studio:

| Edicí sady Visual Studio                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2017        | 08860 |
| Visual Studio Professional 2017      | 08862 |
| Visual Studio Test Professional 2017 | 08866 |

Pokud `StorePID.exe` úspěšně platí kód product key, vrátí `%ERRORLEVEL%` 0. V případě nalezení chyb, vrátí jednu z následujících kódů, v závislosti na podmínce chyby:

| Chyba                     | Kód |
|---------------------------|------|
| `PID_ACTION_SUCCESS`      | 0    |
| `PID_ACTION_NOTINSTALLED` | 1    |
| `PID_ACTION_INVALID`      | 2    |
| `PID_ACTION_EXPIRED`      | 3    |
| `PID_ACTION_INUSE`        | 4    |
| `PID_ACTION_FAILURE`      | 5    |
| `PID_ACTION_NOUPGRADE`    | 6    |

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud se žádný z kroků pro řešení potíží, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také

* [Instalace sady Visual Studio](../install/install-visual-studio.md)
* [Vytvoření offline instalace sady Visual Studio](../install/create-an-offline-installation-of-visual-studio.md)
