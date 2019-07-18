---
title: Nastavení správců pro cloudová předplatná | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: lank
ms.date: 07/17/2019
ms.topic: conceptual
description: Nastavení správců pro cloudová předplatná
ms.openlocfilehash: 62a350e6061444e3c75878dfd89739011c4641d5
ms.sourcegitcommit: 57866dd72fd0e15ce61128df70729b427a2d02eb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/18/2019
ms.locfileid: "68315209"
---
# <a name="set-up-administrators-for-visual-studio-cloud-subscriptions"></a>Nastavení správců pro cloudová předplatná sady Visual Studio

Cloudová předplatná sady Visual Studio spravuje správci. Tito uživatelé můžou přiřazovat předplatná, upravovat přiřazení, přidávat nebo odstraňovat předplatná a provádět další úlohy správy předplatných.

## <a name="the-azure-subscription-owner-is-the-first-administrator"></a>Vlastníkem předplatného Azure je první správce.

Při nákupu cloudových předplatných sady Visual Studio se jako vlastník předplatného Azure, který se používá k nákupu, automaticky nastaví jako správce těchto předplatných.

Můžete si koupit cloudová předplatná prostřednictvím [Visual Studio Marketplace](https://marketplace.visualstudio.com/subscriptions)nebo kontaktovat poskytovatele Cloud Solution Provider. Pokud si koupíte Visual Studio Marketplace na konci nákupu, budete mít k dispozici možnost spravovat uživatele. Výběrem této možnosti přejdete na portál pro správu předplatných sady Visual [https://manage.visualstudio.com](https://manage.visualstudio.com)Studio –.

Po zakoupení předplatných můžete kdykoli navštívit [portál pro správu portálu](https://manage.visualstudio.com) . Stačí se přihlásit k portálu a vybrat příslušné předplatné Azure v levém horním a horním rohu.

Jako vlastník předplatného Azure, který se používá k nákupu cloudových předplatných, můžete také přiřadit další správce.

## <a name="add-administrators"></a>Přidat správce

Přidání správců:

1. Připojte se k webu Azure Portal na adrese [Portal.Azure.com](https://portal.azure.com).
2. Přihlaste se pomocí účtu, který jste použili k nákupu cloudových předplatných sady Visual Studio.
3. V levém navigačním podokně přejděte dolů na **cost management + fakturace**.
4. V seznamu **Moje předplatné** vyberte předplatné Azure, které jste použili k nákupu.
5. Klikněte na **řízení přístupu**, které se nachází v horní části seznamu v levém navigačním podokně.
6. V horní části stránky klikněte na kartu **Přidat** .
7. Klikněte na tlačítko **přidat přiřazení role**.
8. V podokně rozletět na pravé straně klikněte v horní části podokna na rozevírací nabídku **role** , přejděte dolů a vyberte **Správce přístupu uživatele**.
9. V seznamu uživatelů se posuňte dolů k uživateli, který chcete nastavit jako správce, a vyberte je. 
10. Klikněte na **Uložit**.
11. Kliknutím na kartu **přiřazení rolí** ověřte, že uživatel, který jste vybrali, se teď zobrazí jako správce přístupu uživatele.

Nový správce se teď může přihlásit k [portálu pro správu](https://manage.visualstudio.com), vybrat stejné předplatné Azure, které se použilo k nákupu předplatných cloudu, ze seznamu v levém horním rohu stránky a začít spravovat tato předplatná.

> [!NOTE]
> Pokud se zobrazí uživatelé s přístupem k úpravám cloudových předplatných, která jste nevytvořili jako správci, můžou mít v předplatném Azure role, které jim umožní spravovat předplatná. Mezi tyto role patří: vlastník, přispěvatel, správce služeb nebo spolusprávce. Další informace najdete na webu [Přidání správců fakturace](/azure/devops/organizations/billing/add-backup-billing-managers?view=vsts).

Informace o cloudových předplatných sady Visual Studio najdete v [přehledu](vscloud-overview.md) v části nákup předplatných. Pokud si chcete koupit cloudové předplatné sady Visual Studio, [https://marketplace.visualstudio.com/subscriptions](https://marketplace.visualstudio.com/subscription)navštivte Visual Studio Marketplace na adrese.
