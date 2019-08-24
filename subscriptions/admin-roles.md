---
title: Role správce super a správce na portálu pro správu
author: evanwindom
ms.author: lank
manager: lank
ms.date: 08/21/2019
ms.topic: conceptual
description: Přečtěte si o rolích správce superuživatele a správců a postup přiřazení správců.
ms.openlocfilehash: 1beda505008815b87a0de98ee597d7b5ec97693d
ms.sourcegitcommit: c90a998716b3dfa614dedc61a1bea515364efbec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/23/2019
ms.locfileid: "70001428"
---
# <a name="super-admins-and-administrators-for-visual-studio-subscription-agreements"></a>Super správci a správci pro smlouvy o předplatném sady Visual Studio

Na novém portálu pro správu předplatných sady Visual Studio jsou k dispozici dvě různé role pro multilicenční zákazníky. Tyto role jsou jako role primárního/informačního kontaktu a role správce předplatných, které se používají v VLSC.

**Super správci:** Při počátečním nastavování organizace se primární nebo informační kontakt ve výchozím nastavení stal nadtypem správce. Primární nebo informační kontakt se může rozhodnout, že přiřadí další superuživatele nebo správce. Správce Super může přidat a odebrat další správce i předplatitele. Pokud je v systému více než dva Super správci, může nadstraněný správce odstranit všechny kromě poslední dvě pro zabezpečení.

**Systémů** Správce může být přiřazen pouze správci super. Správce může spravovat pouze předplatitele v rámci smluv, ke kterým je správce superuživatele přiřazovat.

## <a name="assigning-administrators"></a>Přiřazování správců
Přiřazení nových správců (správcům):
1. Přihlaste https://manage.visualstudio.com se k používání e-mailové adresy, která je přiřazená jako nadsprávce na smlouvě, jejímž prostřednictvím bylo předplatné zakoupilo.
2. Klikněte na kartu s názvem **Správa správců**.
3. Klikněte na **Přidat**.
   > [!div class="mx-imgBorder"]
   > ![Přidat správce](_img/admin-roles/add-admins.png)
4. Vyplňte formulář s informacemi o novém Správci.  
   > [!div class="mx-imgBorder"]
   > ![Přidat formulář správce](_img/admin-roles/add-form.png)

   > [!NOTE]
   > Pokud chcete, aby tento správce mohl přiřadit další správce, nezapomeňte zaškrtnout políčko **správce Super** .

5. Když kliknete na **Přidat** a přiřadíte nového správce, obdrží jim e-mail, aby se přihlásil k portálu.  

## <a name="resources"></a>Prostředky
- [Podpora správy a předplatných sady Visual Studio](https://visualstudio.microsoft.com/support/support-overview-vs)

## <a name="next-steps"></a>Další postup
- Informace o tom, jak [přiřadit odběry](assign-license.md)
- Další informace o plném rozsahu [výhod](https://visualstudio.microsoft.com/vs/benefits/) předplatného
- [Nastavit předvolby smlouvy](admin-prefs.md) 


