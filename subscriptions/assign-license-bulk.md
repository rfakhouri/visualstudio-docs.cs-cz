---
title: Přiřazení licencí skupinám uživatelů pro předplatná sady Visual Studio | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/24/2019
ms.topic: conceptual
description: Zjistěte, jak můžou správci přiřazovat licence k několika předplatitelům.
ms.openlocfilehash: 7d54dcf3cf3e7fea7845a4e9a0053de4ba734ae9
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/29/2019
ms.locfileid: "68611904"
---
# <a name="assign-subscriptions-to-multiple-users"></a>Přiřazení předplatných více uživatelům
Portál pro správu předplatných umožňuje přidat uživatele v jednom okamžiku nebo ve velkých skupinách.  Chcete-li přidat jednotlivé uživatele, přečtěte si téma [přidání jednotlivých uživatelů](assign-license.md).

## <a name="use-bulk-add-to-assign-subscriptions"></a>Použití hromadného přidání k přiřazení předplatných
1. Přihlaste se na portál pro správu předplatných sady Visual Studio na adrese https://manage.visualstudio.com.
2. Pokud chcete najednou přidat víc odběratelů, přejděte na kartu **Spravovat předplatitele** . Na pásu karet nahoře klikněte na hromadně **Přidat**.
   > [!div class="mx-imgBorder"]
   > ![Přidat několik předplatitelů](media/add-multiple-subscribers.png)

2. Hromadné přidání používá šablonu Microsoft Excelu k nahrání informací o odběrateli. V dialogovém okně nahrát několik předplatitelů klikněte na **Stáhnout** a stáhněte šablonu.
   > [!div class="mx-imgBorder"]
   > ![Stáhněte si excelovou šablonu pro nahrání více odběratelů.](media/download-template-upload-subscribers.png)
   >
   > [!NOTE]
   > Vždy stáhnout nejnovější verzi této šablony. Pokud používáte starší verzi, může hromadné nahrání selhat.

3. V tabulce aplikace Excel vyplňte pole informacemi pro jednotlivce, ke kterým chcete přiřadit odběry. (*Odkaz* je volitelné pole.) Uložte soubor místně, až budete hotovi.

   Pro zajištění hladkého nahrávání si dodržujte následující osvědčené postupy:

    - Zajistěte, aby žádná pole formuláře neobsahovala čárky.
    - Odebrat mezery před a za poli formuláře.
    - Ujistěte se, že názvy uživatelů neobsahují nadbytečné mezery mezi dvěma částmi jména a příjmení (například pokud má osoba jméno se dvěma částmi, například "Maggie květen"), měla by být zadána jako "MaggieMay", protože systém neořízne nadbytečné místo.)

4. Vraťte se na portál pro správu předplatných sady Visual Studio. V dialogovém okně **nahrát několik předplatitelů** klikněte na **Procházet**.
   > [!div class="mx-imgBorder"]
   > ![Pokud chcete nahrát několik předplatitelů, přejděte k uložené šabloně.](media/bulk-add-browse-saved-template.png)

5. Přejděte do excelového souboru, který jste uložili, a pak klikněte na **OK**.
   > [!div class="mx-imgBorder"]
   > ![Nahrání excelové šablony pro nahrání více předplatitelů](media/bulk-upload-subscribers.png)

    Zobrazí se dialogové okno s průběhem nahrávání.

    Pokud šablona obsahuje chyby, nahrávání se nezdaří a zobrazí se chyby, abyste mohli šablonu opravit a znovu se pokusit o hromadné nahrání.
   > [!div class="mx-imgBorder"]
   > ![Chybová zpráva, pokud nahrávání více předplatitelů neproběhne úspěšně](media/bulk-add-template-failed.png)

    Po úspěšném nahrání se zobrazí seznam předplatitelů a potvrzovací zpráva.
   > [!div class="mx-imgBorder"]
   > ![Zpráva s potvrzením úspěšného odeslání více předplatitelů](media/bulk-add-template-success.png)

## <a name="next-steps"></a>Další postup
- Chcete přidat jenom jednoho nebo dva předplatitele?  Podívejte se na [přidat jednotlivé uživatele](assign-license.md) .
- Informace o tom, jak [Upravit](edit-license.md) existující odběry
- Potřebujete pomoc? Obraťte [se na podporu správy a předplatných sady Visual Studio](https://visualstudio.microsoft.com/support/support-overview-vs).
