---
title: 'Postupy: odemknout Visual Studio | Microsoft Docs'
ms.custom: 
ms.date: 07/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ffb580a1-8b5d-48f5-b811-87f8036f50ea
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 87d937c456b875afa5234b61b57edb21ba32baf6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-unlock-visual-studio"></a>Postupy: odemknout Visual Studio

Visual Studio můžete vyhodnotit zdarma až 30 dnů. Přihlášení k prostředí IDE rozšiřuje zkušební doby do 90 dnů. Chcete-li pokračovat pomocí sady Visual Studio, odemknutí integrovaného vývojového prostředí a to buď:

- pomocí online předplatného

- zadání kódu product key

## <a name="to-unlock-visual-studio-using-an-online-subscription"></a>Odemknout Visual Studio pomocí předplatné online

Odemknout Visual Studio pomocí předplatné MSDN nebo Visual Studio Team Service přidružený k účtu Microsoft nebo pracovní nebo školní účet:

1. Klikněte na tlačítko "Přihlásit" v pravém horním rohu okna IDE (nebo přejděte na soubor > Nastavení účtu otevřete dialogové okno nastavení účtu a klikněte na tlačítko "Přihlásit").

1. Zadejte pověření pro účet Microsoft nebo pracovní nebo školní účet. Visual Studio vyhledá předplatné sady Visual Studio nebo Visual Studio Team Services předplatné spojené s vaším účtem.

> [!IMPORTANT]
> Visual Studio automaticky vyhledá přidružené předplatné online při připojení k účtu Visual Studio Team Services z okno nástroje Team Explorer. Jakmile se připojíte k účtu Visual Studio Team Services, můžete přihlásit pomocí společnosti Microsoft a pracovní nebo školní účty. Pokud předplatné online existuje pro tento uživatelský účet, Visual Studio IDE automaticky odemknout za vás.

## <a name="to-unlock-visual-studio-with-a-product-key"></a>Odemknout Visual Studio s kódem product key

1. Vyberte **soubor**, **nastavení účtu** otevřete dialogové okno nastavení účtu a klikněte na **licence s kódem Product Key** odkaz.

Zadejte kód product key v poskytnutém prostoru.

> [!TIP]
> Předběžné verze sady Visual Studio nemusí kódy product key. Musíte se přihlásit k prostředí IDE používat předběžné verze.

## <a name="address-license-problem-states"></a>Vyřešte problém stavy licencí

### <a name="update-stale-licenses"></a>Aktualizaci zastaralé licencí

 Možná jste viděli níže zprávu, která přechází zastaralé v sadě Visual Studio, který čte, licence "licence přešel zastaralé a musí se aktualizovat."

 ![Visual Studio starý licenční zpráv](../ide/media/vs2017_stale-license.png)

 Tato zpráva znamená, že pokud vaše předplatné může být stále platné, licence, které tokenu Visual Studio použije udržovat vaše předplatné aktuální nebyla aktualizovat a přešel zastaralé kvůli jednomu z následujících důvodů:

- Nepoužili Visual Studio nebo měla bez připojení k Internetu pro delší dobu.
- Odhlásili jste se od aplikace Visual Studio.

Před token licence přestane starý, Visual Studio nejprve zobrazí zprávu s upozorněním s dotazem, znovu zadat přihlašovací údaje.

Pokud není znovu zadat přihlašovací údaje, token začne přejděte zastaralé a dialogovém okně Nastavení účtu se dozvíte, jak dlouho mají ponecháno před plně vyprší platnost vašeho tokenu. Po vypršení platnosti tokenu, musíte znovu zadat přihlašovací údaje pro tento účet nebo licence s jinou metodu vyšší, než budete pokračovat, pomocí sady Visual Studio.

> [!Important]
> Pokud používáte Visual Studio po delší dobu v prostředích s omezeným nebo žádný přístup k Internetu, používejte kód product key k odemknutí Visual Studio, aby se zabránilo přerušení.

### <a name="update-expired-licenses"></a>Aktualizovat vypršela platnost licence

 Pokud vypršela platnost předplatného úplně a již nemáte přístupová práva k sadě Visual Studio, musíte obnovit předplatné nebo přidat jiný účet, který má předplatné. Chcete-li zobrazit další informace o licenci, kterou používáte, přejděte na **soubor**, **nastavení účtu** a prohlédněte si informace o licenci na pravé straně dialogového okna. Pokud máte jiné předplatné přidružený k jinému účtu, tento účet přidejte do **všechny účty** seznamu na levé straně dialogového okna tak, že vyberete **přidat účet...**  odkaz.

## <a name="see-also"></a>Viz také

* [Přihlášení k sadě Visual Studio](../ide/signing-in-to-visual-studio.md)
 
