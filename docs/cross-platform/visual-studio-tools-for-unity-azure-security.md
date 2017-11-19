---
title: "Visual Studio Tools for Unity Azure návod zabezpečení | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: F4FD6E1C-EA64-4613-BDDE-6E4E5CCF983E
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: d036d180fddcce443debe3d7917415380187994c
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="update-unity-mono-security-certificate-store"></a>Úložiště certifikátů zabezpečení Unity Mono aktualizace

Na Unity Mono se dodává s úložišti prázdný certifikátu a proto nedůvěřuje libovolné lokalitě. Další informace o to na [Mono zabezpečení – nejčastější dotazy](http://www.mono-project.com/docs/faq/security/).

Aby bylo možné připojit k Azure bez ignoruje TLS / SSL, musí být úložiště certifikátů Unity Mono aktualizovat.

## <a name="using-mozroots-to-install-certificates"></a>Použití mozroots k instalaci certifikátů

Nástroj mozroots je součástí Mono. Se stáhne a nainstaluje na Mozilla seznam kořenových certifikátů.

1. Otevřete okno příkazového řádku terminálu.

2. Přejděte v terminálu k **C:\Program Files\Unity\Editor\Data\MonoBleedingEdge\bin >** adresáře. Přesné umístění se můžou lišit v závislosti na tom, kam jste nainstalovali Unity na místním počítači.

3. Zadejte následující příkaz a stiskněte tlačítko **Enter** spouštět:

  `mono ..\lib\mono\4.5\mozroots.exe --sync --import`

4. Měli byste obdržet následující výstup (i když číslo nebo přidat certifikáty se můžou lišit):

  ```
  Downloading from 'https://hg.mozilla.org/releases/mozilla-release/raw-file/default/security/nss/lib/ckfw/builtins/certdata.txt'...
  Importing certificates into user store...
  1 new root certificates were added to your trust store.
  Import process completed.
  ```

5. Teď byste měli spustit příklad projektu, aniž by mu musela TLS související chyby.

## <a name="next-step"></a>Další krok

* [Testovací připojení klienta](visual-studio-tools-for-unity-azure-connection.md)
