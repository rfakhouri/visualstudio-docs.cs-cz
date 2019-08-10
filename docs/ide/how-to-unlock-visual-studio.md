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
ms.openlocfilehash: fe0aa86be242e9a7e7ed8d877944c66247718167
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926292"
---
# <a name="how-to-unlock-visual-studio"></a>Postupy: Odemknout Visual Studio

Můžete si vyzkoušet Visual Studio zdarma až po dobu 30 dnů. Přihlášení k prostředí IDE rozšiřuje zkušební období na 90 dní. Chcete-li pokračovat v používání sady Visual Studio, odemkněte rozhraní IDE buď pomocí:

- používání online předplatného

- zadání kódu Product Key

## <a name="to-unlock-visual-studio-using-an-online-subscription"></a>Odemčení sady Visual Studio pomocí online předplatného

Pokud chcete aplikaci Visual Studio odemknout pomocí předplatného sady Visual Studio nebo organizace Azure DevOps, která je přidružená k účet Microsoft, nebo pracovnímu nebo školnímu účtu:

1. Klikněte na tlačítko **Přihlásit** v pravém horním rohu integrovaného vývojového prostředí (nebo přejít na**Nastavení účtu** **souboru** > a otevřete dialogové okno **Nastavení účtu** a klikněte na tlačítko **Přihlásit** se).

1. Zadejte přihlašovací údaje pro účet Microsoft nebo pracovní nebo školní účet. Visual Studio najde předplatné sady Visual Studio nebo organizaci Azure DevOps, která je přidružená k vašemu účtu.

> [!IMPORTANT]
> Když se připojíte k organizaci Azure DevOps z okna nástroje **Team Explorer** , Visual Studio automaticky vyhledá přidružené online předplatné. Když se připojíte k organizaci Azure DevOps, můžete se přihlásit pomocí Microsoft i pracovního nebo školního účtu. Pokud pro tento uživatelský účet existuje s online předplatným, sada Visual Studio automaticky odemknout rozhraní IDE za vás.

## <a name="to-unlock-visual-studio-with-a-product-key"></a>K odemknutí sady Visual Studio s kódem product key

1. Zvolením**Možnosti účet** **souboru** > otevřete dialogové okno **Nastavení účtu** a pak vyberte **licenci s odkazem na kód Product Key** .

1. Zadejte kód product key v poskytnutém prostoru.

> [!TIP]
> Předběžné verze sady Visual Studio nemají kódy Product Key. Chcete-li použít předběžné verze, je nutné se přihlásit k integrovanému vývojovému prostředí.

## <a name="address-license-problem-states"></a>Adresové stavy problémů s licencí

### <a name="update-stale-licenses"></a>Aktualizace zastaralých licencí

Možná jste viděli následující zprávu s oznámením, že vaše licence bude v aplikaci Visual Studio zastaralá. Čte "vaše licence prošla zastaralým a je nutné ji aktualizovat."

![Zpráva zastaralá licence sady Visual Studio](../ide/media/vs2017_stale-license.png)

Tato zpráva znamená, že i když může být předplatné stále platné, aplikace Visual Studio s tokenem licence zachová aktuální předplatné a v důsledku toho je zastaralá kvůli jednomu z následujících důvodů:

- Nepoužívali jste aplikaci Visual Studio nebo nemáte k dispozici žádné připojení k Internetu po delší dobu.
- Odhlásili jste se od sady Visual Studio.

Před zastaralým tokenem licence Visual Studio nejprve zobrazí zprávu s upozorněním, že je třeba znovu zadat přihlašovací údaje.

Pokud přihlašovací údaje nezadáte znovu, zahájí se platnost tokenu a dialogové okno **Nastavení účtu** vám ukáže, kolik dní zbývá před úplným vypršením platnosti tokenu. Po vypršení platnosti tokenu musíte znovu zadat svoje přihlašovací údaje pro účet, aby bylo možné pokračovat v používání sady Visual Studio.

> [!Important]
> Pokud používáte Visual Studio pro rozšířené tečky v prostředích s omezeným nebo žádným přístupem k Internetu, měli byste použít kód Product Key k odemknutí sady Visual Studio, abyste se vyhnuli přerušení.

### <a name="update-expired-licenses"></a>Aktualizace licencí s vypršenou platností

Pokud vašemu předplatnému vypršela platnost a už nemáte přístupová práva k aplikaci Visual Studio, musíte si obnovit předplatné nebo přidat další účet s předplatným. Pokud chcete zobrazit další informace o licenci, kterou používáte, přejděte na**Nastavení účtu** **soubor** > a podívejte se na informace o licencích na pravé straně dialogového okna. Pokud máte k jinému účtu přidruženo jiné předplatné, přidejte tento účet do seznamu **všechny účty** na levé straně dialogového okna tak, že vyberete odkaz **Přidat účet** .

## <a name="see-also"></a>Viz také:

* [Přihlášení k sadě Visual Studio](../ide/signing-in-to-visual-studio.md)
