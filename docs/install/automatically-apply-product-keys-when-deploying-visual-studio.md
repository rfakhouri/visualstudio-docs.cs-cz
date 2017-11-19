---
title: "Automatické použití kódů product key při nasazení sady Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: 
ms.technology: vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: 157ef18baa38169790fe528fd3358fbea8ff6196
ms.sourcegitcommit: 26419ab0cccdc30d279c32d6a841758cfa903806
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/11/2017
---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>Automatické použití kódů product key při nasazení sady Visual Studio
Můžete použít kód product key prostřednictvím kódu programu jako součást skript, který slouží k automatizaci nasazení sady Visual Studio. Můžete nastavit kód product key na zařízení prostřednictvím kódu programu buď při instalaci sady Visual Studio nebo po dokončení instalace.

## <a name="apply-the-license-after-installation"></a>Použít licence, které jsou po instalaci
 Nainstalovaná verze sady Visual Studio s kódem product key můžete aktivovat pomocí `StorePID.exe` nástroj na cílových počítačích, v bezobslužném režimu. `StorePID.exe`je nástroj pro program, který se instaluje s Visual Studio 2017 v následujícím výchozím umístění: <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

 Spustit `StorePID.exe` se zvýšenými oprávněními, buď pomocí agenta System Center nebo příkazového řádku se zvýšenými oprávněními. Po ní následuje kód product key a kód produktu Microsoft (MPC).

>[!IMPORTANT]
> Nezapomeňte zahrnout pomlček kód product key.

 ```
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
V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránku Tipy pro odstraňování potíží. Taky můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj v prostředí Visual Studio IDE nebo ke sdílení návrh s nám na [UserVoice](https://visualstudio.uservoice.com/forums/121579). Můžete sledovat problémy produktu v [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/)a klást otázky a odpovědi. Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím našich [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio) (vyžaduje [Githubu](https://github.com/) účtu).

## <a name="see-also"></a>Viz také
 * [Instalaci sady Visual Studio](../install/install-visual-studio.md)
 * [Vytvoření offline instalace sady Visual Studio](../install/create-an-offline-installation-of-visual-studio.md)
