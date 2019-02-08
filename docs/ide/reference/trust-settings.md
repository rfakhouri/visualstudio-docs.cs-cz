---
title: Důvěřovat nastavení pro soubory a složky
description: Zjistěte, jak změnit nastavení vztahu důvěryhodnosti pro soubory a složky k lepšímu zabezpečení sady Visual Studio.
author: abuchholtzau
ms.author: allisb
ms.date: 09/05/2018
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Environment.PathTrustOptions
helpviewer_keywords:
- file security
- folder security
- mark of the web
- trusted files
- trusted folders
ms.openlocfilehash: 011673bca7be569b5b350dc264148d5a7890d39c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55954944"
---
# <a name="configure-trust-settings-for-files-and-folders"></a>Konfigurace nastavení vztahu důvěryhodnosti pro soubory a složky

Visual Studio vyzve k zadání schválení uživatele před otevřením projekty, které mají [označit webu](/previous-versions/windows/internet-explorer/ie-developer/compatibility/ms537628(v=vs.85)). Pro zvýšení zabezpečení, můžete taky nakonfigurovat Visual Studio výzva ke schválení uživatele před otevřením kterýkoli soubor nebo složku, která má označení atribut webové nebo, který není označen jako *důvěryhodné*. Ve výchozím nastavení jsou zakázány kontroly souborů a složek.

> [!WARNING]
> Stále se ujistěte, že soubor, složku nebo řešení pochází z důvěryhodné osoby nebo důvěryhodného umístění před schválením ho.

## <a name="configure-trust-settings"></a>Konfigurace nastavení vztahu důvěryhodnosti

Chcete-li změnit nastavení vztahu důvěryhodnosti, postupujte podle těchto kroků:

1. Otevřít **nástroje** > **možnosti** > **nastavení zabezpečení** a vyberte **nakonfigurovat nastavení zabezpečení** odkaz v v pravém podokně.

2. Vyberte úroveň kontroly, které chcete pro soubory a složky. U každé z nich může mít jiné kontroly. Možnosti jsou:

   * **Ověření**: Visual Studio neprovádí žádné kontroly.

   * **Ověřte označit atribut webové**: Pokud je soubor nebo složku označen atribut webové, Visual Studio a ostatní porty blokuje požádá o oprávnění k otevření.

   * **Ověřte cestu je důvěryhodný**: Pokud cestu souboru nebo složky, které nejsou součástí sady **důvěryhodné cesty** seznamu, sady Visual Studio a ostatní porty blokuje požádá o oprávnění k otevření.

   ![Možnosti ověřování vztahu důvěryhodnosti](media/trust-settings.png)

## <a name="add-trusted-paths"></a>Přidat důvěryhodné cesty

Chcete-li přidat důvěryhodné cesty, postupujte takto:

1. Otevřít **nástroje** > **možnosti** > **nastavení zabezpečení** a vyberte **nakonfigurovat nastavení zabezpečení** odkaz v v pravém podokně.

2. Klikněte na tlačítko **přidat** v **nastavení zabezpečení** dialogového okna a pak vyberte **souboru** nebo **složky**.

3. Vyhledejte a vyberte požadovaný soubor nebo složku, kterou chcete přidat do seznamu důvěryhodných.

   Cesta souboru nebo složky se zobrazí v **důvěryhodné cesty** seznamu.

   ![Přidat důvěryhodné cesty](media/trusted-paths.png)

## <a name="remove-trusted-paths"></a>Odebrat důvěryhodné cesty

Odebrání důvěryhodných cest, postupujte podle těchto kroků:

1. Otevřít **nástroje** > **možnosti** > **nastavení zabezpečení** a vyberte **nakonfigurovat nastavení zabezpečení** odkaz v v pravém podokně.

2. Vyberte cestu, která byste chtěli odebrat **důvěryhodné cesty** seznamu a potom klikněte na tlačítko **odebrat**.

   > [!TIP]
   > Chcete-li vybrat více položek podržte **Shift** po vybrání cesty.

   Odeberou se z vybrané cesty **důvěryhodné cesty** seznamu.
