---
title: Úprava předplatných na portálu pro správce | Dokumentace Microsoftu
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: conceptual
description: Zjistěte, jak můžou správci upravovat přiřazení předplatného.
searchscope: VS Subscription
ms.openlocfilehash: d3dbc2e05d85ed8277d7a7c0f530dfa92da7dba6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946234"
---
# <a name="editing-visual-studio-subscription-assignments"></a>Úprava přiřazení předplatného sady Visual Studio

Jako správce předplatného můžete provedete změny přiřazených osobám ve vaší organizaci předplatných.  Tento článek popisuje typy změny, které můžete provádět a popisuje kroky potřebné.

## <a name="making-changes-to-subscriber-information"></a>Informace o provádění změn
Předplatitel sady informace, opravte chyby nebo aktualizovat informace můžete upravit.

Chcete-li upravit odběratele, vyberte symbol tří teček (...), které se zobrazují vedle e-mailovou adresu odběratele, když najedete myší nad ním. Zobrazí se rozevírací seznam.  Vyberte **upravit** upravit podrobné údaje o předplatitelích společnosti. Můžete také dvakrát kliknout na účastníka řádků v mřížce, chcete-li otevřít okno pro úpravu.
> [!div class="mx-imgBorder"]
> ![Vybrat odběratele k úpravě](_img/edit-license/select-subscriber.png)

Můžete aktualizovat účastníka křestní jméno, příjmení, zemi, jazyk a soubory ke stažení. Upravit informace na odběratele a potom klikněte na **Uložit**.

   > [!NOTE]
   > Pokud potřebujete změnit úroveň předplatného pro odběratele, je potřeba odstranit uživatele z portálu a znovu přidat. Úrovní předplatného se nedají upravovat.

## <a name="editing-multiple-subscribers-using-bulk-edit"></a>Úpravy pomocí hromadně upravit několik předplatitelů

Můžete upravit několik předplatitelů najednou pomocí procesu hromadné úpravy. Tato funkce se používá především pro organizace, které jsou projít firemní e-mailová adresa změní nebo pokud se organizace rozhodla k omezení přístupu k souborům ke stažení.

   > [!IMPORTANT]
   > Předplatné úrovně (například Enterprise, Professional, atd.) a identifikátory GUID předplatných se nedá změnit.  Při pokusu o nahrání s následujícími položkami změnit nahrávání se nezdaří.

1. Chcete-li upravit několik předplatitelů najednou, přejděte na kartu předplatitele. Na pásu karet v horní části klikněte na tlačítko **hromadných úprav**.

2. Hromadné úpravy pomocí šablony aplikace Excel úpravy na informace o odběrateli. V okně hromadně upravit, klikněte na tlačítko **exportujte tuto tabulku** stáhnout aktuální seznam předplatitelů, včetně všech svých informací.
   > [!div class="mx-imgBorder"]
   > ![Úpravy licenci - Export hromadné úpravy seznamu](_img/edit-license/edit-license-bulk-edit-export.png)

3. V dalším kroku uložte soubor místně, takže můžete snadno najít a proveďte potřebné změny před odesláním. K zajištění úspěšně nahrávaly **neupravujte úrovni předplatného nebo GUID předplatného** jako to uděláte tak způsobí, že se nezdaří.

4. Vrátit k portálu pro správu předplatných sady Visual Studio a v dialogovém okně hromadných úprav, klikněte na tlačítko **Procházet**. Vyberte Excelový soubor, který jste uložili a klikněte na tlačítko **OK**. Průběh nahrávání se zobrazí na obrazovce.
   > [!div class="mx-imgBorder"]
   > ![Úpravy licenci - hromadné úpravy odesílání souborů](_img/edit-license/edit-license-bulk-file-upload1.png)

5. Po nahrání souboru, zobrazí se upozornění oznamující, že bylo úspěšné. V tomto okamžiku vaše změny se projeví ve informace o odběrateli.
