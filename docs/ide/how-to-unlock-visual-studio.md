---
title: 'Postupy: Odemknout Visual Studio'
titleSuffix: ''
ms.date: 03/30/2019
ms.topic: conceptual
ms.assetid: ffb580a1-8b5d-48f5-b811-87f8036f50ea
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.openlocfilehash: 2bb6de32188abb11e0286c200383bdb1e8fb12f7
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/02/2019
ms.locfileid: "58856817"
---
# <a name="how-to-unlock-visual-studio"></a>Postupy: Odemknout Visual Studio

Můžete si vyzkoušet Visual Studio zdarma až po dobu 30 dnů. Přihlašování do integrovaného vývojového prostředí rozšiřuje zkušební období na 90 dní. Chcete-li pokračovat pomocí sady Visual Studio, odemknete rozhraní IDE podle:

- prostřednictvím online předplatného

- zadání kódu product key

## <a name="to-unlock-visual-studio-using-an-online-subscription"></a>Odemknout prostřednictvím online předplatného sady Visual Studio

K odemknutí sady Visual Studio pomocí předplatného sady Visual Studio nebo organizace Azure DevOps přidružené k účtu Microsoft nebo pracovní nebo školní účet:

1. Zvolte **přihlášení** tlačítko v pravém horním rohu integrovaného vývojového prostředí (nebo můžete přejít na **souboru** > **nastavení účtu** otevřít **nastavení účtu**  dialogové okno a zvolte **přihlášení** tlačítko).

1. Zadejte přihlašovací údaje pro účet Microsoft nebo pracovní nebo školní účet. Visual Studio vyhledá předplatné sady Visual Studio nebo spojené s vaším účtem organizace Azure DevOps.

> [!IMPORTANT]
> Visual Studio online přidružených předplatných automaticky vyhledá, při připojení k organizaci Azure DevOps z **Team Exploreru** panelu nástrojů. Při připojení k organizaci Azure DevOps se můžete přihlásit pomocí Microsoft a pracovní nebo školní účty. Pokud pro tento uživatelský účet existuje s online předplatným, sada Visual Studio automaticky odemknout rozhraní IDE za vás.

## <a name="to-unlock-visual-studio-with-a-product-key"></a>K odemknutí sady Visual Studio s kódem product key

1. Vyberte **souboru** > **nastavení účtu** otevřít **nastavení účtu** dialogového okna a klikněte na tlačítko **licence s kódem Product Key** odkaz.

1. Zadejte kód product key v poskytnutém prostoru.

> [!TIP]
> Předběžné verze sady Visual Studio nemají žádné kódy product key. Musíte se přihlásit k prostředí IDE použití předběžných verzí.

## <a name="address-license-problem-states"></a>Stavy problém licenční adresy

### <a name="update-stale-licenses"></a>Aktualizovat zastaralé licence

 Možná jste viděli následující zpráva, která říká, že vaše licence bude zastaralé v sadě Visual Studio. Načte, "vaše licence je prošlá a musí se aktualizovat."

 ![Zpráva zastaralé licence Visual Studio](../ide/media/vs2017_stale-license.png)

 Tato zpráva znamená, že vaše předplatné může být stále platná, licenci, kterou token Visual Studio používá k zajištění aktuálnosti vaše předplatné se aktualizují a je prošlá kvůli jednomu z následujících důvodů:

- Nepoužili sady Visual Studio nebo měli bez připojení k Internetu pro delší dobu.
- Odhlásili jste se od sady Visual Studio.

Předtím, než půjde zastaralé token licence, sada Visual Studio nejprve zobrazí zpráva s dotazem, můžete znovu zadat přihlašovací údaje.

Pokud není znovu zadat přihlašovací údaje, token se začne přejít zastaralé a **nastavení účtu** dialogové okno zjistíte, kolik dní zbývá před plně vyprší platnost tokenu. Po vypršení platnosti tokenu, je nutné znovu zadat své přihlašovací údaje pro účet předtím, než můžete pokračovat v používání sady Visual Studio.

> [!Important]
> Pokud používáte Visual Studio po delší dobu v prostředích s omezením nebo bez připojení k Internetu, by měl použít kód product key k odemknutí sady Visual Studio, aby se zabránilo přerušení.

### <a name="update-expired-licenses"></a>Aktualizovat vypršela platnost licence

 Pokud vypršela platnost vašeho předplatného úplně a už nebude mít přístupová práva ke službě Visual Studio, musíte předplatné nebo přidat další účet, který má předplatné. Chcete-li zobrazit další informace o licenci, kterou používáte, přejděte na **souboru** > **nastavení účtu** a podívejte se na informace o licenci na pravé straně dialogového okna. Pokud máte jiné předplatné spojené s jiným účtem, přidejte daný účet do **všechny účty** seznamu na levé straně dialogového okna tak, že vyberete **přidat účet** odkaz.

## <a name="see-also"></a>Viz také:

* [Přihlášení k sadě Visual Studio](../ide/signing-in-to-visual-studio.md)
