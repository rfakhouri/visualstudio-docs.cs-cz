---
title: Upravit odběry na portálu pro správu | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/28/2019
ms.topic: conceptual
description: Přečtěte si, jak můžou správci upravovat přiřazení předplatného.
ms.openlocfilehash: e55cee74f861973e3cc29e3f19dc9b31a107f437
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605650"
---
# <a name="edit-visual-studio-subscription-assignments"></a>Upravit přiřazení předplatných sady Visual Studio
Jako správce předplatného můžete provádět změny v předplatných přiřazených jednotlivcům ve vaší organizaci.  Tento článek popisuje typy změn, které lze provést, a poskytuje potřebné kroky.

## <a name="change-subscriber-information"></a>Změna informací o odběrateli
Můžete upravit informace předplatitele a opravit chyby nebo aktualizovat informace.

Pokud chcete odběratele upravit, vyberte tři tečky (...), které se zobrazí vedle e-mailové adresy předplatitele, když na ni najedete myší. Zobrazí se rozevírací seznam.  Výběrem **Upravit** upravíte podrobnosti odběratele. Můžete také dvakrát kliknout na řádek předplatitele v mřížce a otevřít tak okno pro úpravy.
> [!div class="mx-imgBorder"]
> ![Vyberte odběratele, kterého chcete upravit.](_img/edit-license/select-subscriber.png)

Můžete aktualizovat křestní jméno, příjmení, zemi, jazyk a soubory odběratele. Upravte informace předplatitele a potom klikněte na **Uložit**.

   > [!NOTE]
   > Pokud potřebujete změnit úroveň předplatného pro předplatitele, budete muset uživatele odstranit z portálu a znovu ho přidat. Úrovně předplatného není možné upravovat.

## <a name="edit-multiple-subscribers-using-bulk-edit"></a>Úprava více odběratelů pomocí hromadné úpravy
Pomocí procesu hromadného úprav můžete upravovat více předplatitelů najednou. Tato funkce se primárně používá pro organizace, které procházejí se změnami firemních e-mailových adres, nebo pokud se organizace rozhodla omezit přístup k souborům ke stažení.

   > [!IMPORTANT]
   > Úrovně předplatného (tj. Enterprise, Professional atd.) a GUID předplatného se nedají změnit.  Pokud se pokusíte nahrát změny těchto položek, nahrávání se nezdaří.

1. Chcete-li upravit více předplatitelů najednou, přejděte na kartu předplatitelé. Na pásu karet nahoře klikněte na Hromadná **Úprava**.

2. Hromadná úprava používá excelovou šablonu k provádění úprav informací o odběrateli. V poli Hromadná úprava klikněte na **exportovat tento Excel** a Stáhněte si aktuální seznam předplatitelů včetně všech jejich informací.
   > [!div class="mx-imgBorder"]
   > ![Úprava seznamu hromadných úprav pro export licencí](_img/edit-license/edit-license-bulk-edit-export.png)

3. Potom uložte soubor místně, abyste ho mohli snadno najít a provést potřebné změny před jeho odesláním. Aby se zajistilo úspěšné nahrání, neupravujte **na úrovni předplatného nebo identifikátor GUID** předplatného, což způsobí selhání nahrávání.

4. Vraťte se na portál pro správu předplatných sady Visual Studio a v dialogovém okně hromadné úpravy klikněte na **Procházet**. Vyberte excelový soubor, který jste uložili, a klikněte na **OK**. Na obrazovce se zobrazí průběh nahrávání.
   > [!div class="mx-imgBorder"]
   > ![Úprava nahrávání souboru s hromadnou úpravou licencí](_img/edit-license/edit-license-bulk-file-upload1.png)

5. Po nahrání souboru se zobrazí oznámení o tom, že bylo úspěšné. V tomto okamžiku se vaše úpravy projeví v informacích o odběrateli.

## <a name="next-steps"></a>Další postup
- Nápovědu k vyhledání konkrétního předplatného najdete v tématu [hledání](search-license.md)předplatného.
- Potřebujete vytvořit seznam všech vašich předplatných?  Podívejte se na [Export](exporting-subscriptions.md)předplatných.