---
title: Upravit předplatná v portálu správce | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
description: Zjistěte, jak správci můžete upravit přiřazení předplatného.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 9ea5f6bc562ce520be08728facfb6099df95ca4c
ms.sourcegitcommit: 928885ace538bef5b25961358d4f166d648f196a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/27/2018
---
# <a name="editing-visual-studio-subscription-assignments"></a>Úpravy přiřazení předplatné sady Visual Studio

Jako správce předplatného můžete provést změny odběry přiřazeny uživatelům v rámci vaší organizace.  Tento článek popisuje typy změn, můžete provést a poskytuje potřebné kroky. 

## <a name="making-changes-to-subscriber-information"></a>Provádění změn informace o odběru
Můžete upravit informace odběratele opravte chyby nebo aktualizovat informace. 

Chcete-li upravit odběratele, vyberte na výpustky (...), které se zobrazují vedle e-mailová adresa odběratele, při přesunutí ukazatele myši nad ním. Zobrazí se rozevírací seznam.  Vyberte **upravit** upravit podrobnosti odběratele. Můžete také dvakrát klikněte na řádek odběratele v mřížce a otevřete okno Upravit.

   ![Vyberte odběratele, které chcete upravit](_img\edit-license\select-subscriber.png)

Můžete aktualizovat odběrateli křestní jméno, příjmení, země, jazyk a soubory ke stažení. Upravit informace o odběratele a potom klikněte na **Uložit**.

   ![Upravit podrobnosti odběratele](_img\edit-license\edit-subscriber.png)

> [!NOTE]
> Pokud potřebujete změnit úroveň odběr pro odběratele, musíte odstranit uživatele z portálu a znovu přidejte. Předplatné úrovně se nedají upravovat.

## <a name="editing-multiple-subscribers-by-using-bulk-edit"></a>Úprava více odběrateli pomocí hromadné úpravy

Můžete upravit více odběrateli najednou procesem hromadné úpravy. Tato funkce slouží především pro organizace, které jsou průchodu přes firemní e-mailová adresa změny nebo pokud se organizace rozhodla pro omezení přístupu ke stahování. 

> [!IMPORTANT]
> Předplatné úrovně (tj. Enterprise, Professional atd.) a nelze je měnit předplatné identifikátory GUID.  Když zkusíte nahrávaný s následujícími položkami změnit, nahrávání se nezdaří.  

1.  Chcete-li upravit více odběrateli najednou, přejděte na kartu odběratele. Na pásu karet v horní části, klikněte na tlačítko **hromadně upravovat**. 

    ![Úpravy licenci - hromadné úpravy](_img\edit-license\edit-license-bulk-edit.png)

2.  Hromadné úpravy používá šablony aplikace Excel k provádět úpravy informace o odběru. V dialogovém okně Upravit hromadné klikněte na tlačítko **Export to v aplikaci excel** stáhnout aktuální seznam odběratele, včetně všech jejich informací. 

    ![Úpravy licenci - Export provede hromadné úpravy seznamu](_img\edit-license\edit-license-bulk-edit-export.png)

3.  V dalším kroku uložte soubor místně, abyste mohli snadno najít a proveďte potřebné změny před jejich odesláním ji. Chcete-li zaručit úspěšné odeslání, **nemusíte upravovat úrovni předplatného nebo GUID odběru** jako to může způsobit odeslání selhání. 

4.  Vrátit na portál pro správu předplatných Visual Studio a v dialogovém okně hromadně upravovat, klikněte na tlačítko **Procházet**. Vyberte soubor aplikace Excel, který jste uložili a klikněte na tlačítko **OK**. Průběh nahrávání se zobrazí na obrazovce.

    ![Úpravy licenci - hromadné upravuje nahrávání souborů](_img\edit-license\edit-license-bulk-file-upload1.png)

5.  Jakmile jste odeslali soubor, zobrazí se oznámení umožňují vědět, že byla úspěšná. V tomto okamžiku provedené úpravy se projeví v informace o odběrateli. 

    ![Úpravy licenci - dokončení nahrávání provede hromadné úpravy](_img\edit-license\edit-license-bulk-upload-complete.png)


