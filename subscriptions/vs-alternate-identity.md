---
title: Identity pro předplatitele sady Visual Studio
Author: evanwindom
Ms.author: jaunger
Manager: evelynp
Ms.date: 3/15/2018
Ms.topic: Get-Started-Article
Description: How to add an alternate identity for your Visual Studio subscription, to use for VSTS and Azure.
Ms.prod: vs-subscription
Ms.technology: vs-subscriptions
Searchscope: VS Subscription
ms.openlocfilehash: 70bfd305ec35b562fb722fb853016c3df4240ff8
ms.sourcegitcommit: 67374acb6d24019a434d96bf705efdab99d335ee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="identities-for-visual-studio-subscribers"></a>Identity pro předplatitele sady Visual Studio

Když aktivujete předplatné sady Visual Studio, jsme propojit identity (nebo přihlášení), který jste použili při aktivaci s použitím sady Visual Studio předplatné. Tímto způsobem můžete Uvědomujeme si můžete na [portál odběratele Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), v služby VSTS a v Azure.

V služby VSTS jsme zkontrolujte stav předplatného sady Visual Studio pokaždé, když jste přihlášení a můžete udělit funkce automaticky v rámci každého účtu, ve kterém jste členem. Protože tyto funkce jsou zahrnuty jako výhodu předplatitele, je bezplatná můžete přidat jako člena v libovolný účet služby VSTS při použití identity, který je přidružený k vašemu předplatnému Visual Studio.

V Azure, jsme zkontrolujte stav předplatné sady Visual Studio při aktivaci vaší [měsíčního kreditu Azure](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) tedy výhodu předplatitele.

V rámci [portál odběratele Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), bude pravděpodobně možné přidat **alternativní identity**– kromě Identita použitá během aktivace. Dnes nám umožňují přidání alternativní identity, pokud jste použili účet Microsoft předplatné aktivujete. Tento způsob, jak můžete také přidat pracovní nebo školní účet (který používáte při přihlašování sady Visual Studio, Office 365 nebo firemní nebo školní sítě), což umožňuje přístup k služby VSTS pomocí účtu osobní i pracovní nebo školní účet.

## <a name="how-to-add-an-alternate-identity-to-your-visual-studio-subscription"></a>Postup přidání alternativní identity do vašeho předplatného sady Visual Studio

1. Přihlaste se k [portál odběratele Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs).

  > Pokud budete vyzváni k zvolte "osobní účet" nebo "pracovní nebo školní účet", "osobní účet" zvolit (účtu Microsoft).
  >
  > V některých případech budete muset zvolit, protože váš účet Microsoft a pracovní nebo školní účet sdílejí stejnou e-mailovou adresu. I když obě identity používat stejnou e-mailovou adresu, jsou stále samostatné identity s různými profily, nastavení zabezpečení a oprávnění.
  >
  > Od 30. března 2018 už nebudete moct vytvořit účet Microsoft pomocí e-mailu, který používá domény, který je spravován v Azure Active Directory. Stále se můžete přihlásit pomocí této e-mailu jako pracovní účet.

2. Přejděte na **odběry** kartě.

  ![Vyberte předplatná](_img/vs-alternate-identity/choose-subscriptions-my-visual-studio-com-portal.png)

3. V části **související odkazy**, přejděte na **přidání alternativního účtu**.

  ![V části související odkazy přejděte k přidání alternativního účtu](_img/vs-alternate-identity/add-alternate-account-my-visual-studio-com-portal.png)

4. Zadejte svůj pracovní nebo školní účet a zvolte **přidat**.

  ![Zadejte svůj pracovní nebo školní účet](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. Použít pracovní nebo školní účet pro přihlášení ke svému účtu služby VSTS (```https://{youraccount}.visualstudio.com```). Mohou existovat k mírnému zpoždění informace, které chcete rozšířit, tak to zkuste znovu 15 minut později. 

## <a name="faq"></a>Nejčastější dotazy

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>Otázka: Proč služby VSTS nerozpoznal mi jako odběratel Visual Studio?
A: služby VSTS by měl automaticky rozpoznat vaše předplatné při přihlášení pomocí vaší primární nebo alternativní identity. Pokud ne, můžete zkusit několik věcí:

* Zkontrolujte, že máte aktivní předplatné sady Visual Studio, [zahrnuje služby VSTS jako výhody](vs-vsts.md).

* Potvrďte, že používáte přihlášení nebo identitou, která je buď primární nebo alternativní identitu pro vaše předplatné sady Visual Studio.

* Přejděte [portál odběratele Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs) alespoň jednou před přihlášení do služby VSTS.

Pokud služby VSTS stále nerozpoznal vaše předplatné [obraťte se na podporu](https://www.visualstudio.com/team-services/support/)

