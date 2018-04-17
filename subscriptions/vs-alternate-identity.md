---
title: Identity pro předplatitele sady Visual Studio
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 04/10/2018
ms.topic: conceptual
description: Postup přidání alternativní identity pro vaše předplatné sady Visual Studio, používat pro služby VSTS a Azure
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: vs subscription
ms.openlocfilehash: 9a83f78f35b9533c554c81cecd181c00eca05568
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="identities-for-visual-studio-subscribers"></a>Identity pro předplatitele sady Visual Studio

Když aktivujete předplatné sady Visual Studio, jsme propojit identity (nebo přihlášení), který jste použili při aktivaci s použitím sady Visual Studio předplatné. Tímto způsobem můžete Uvědomujeme si můžete na [portál odběratele Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), v aplikaci Visual Studio Team Services (služby VSTS) a v Azure.

V služby VSTS jsme zkontrolujte stav předplatného sady Visual Studio pokaždé, když jste přihlášení a můžete udělit funkce automaticky v rámci každého účtu, ve kterém jste členem.
Protože tyto funkce jsou zahrnuty jako výhodu předplatitele, je bezplatná můžete přidat jako člena v libovolný účet služby VSTS při použití identity, který je přidružený k vašemu předplatnému Visual Studio.

V Azure, jsme zkontrolujte stav předplatné sady Visual Studio při aktivaci vaší [měsíčního kreditu Azure](https://azure.microsoft.com/pricing/member-offers/credit-for-visual-studio-subscribers/) tedy výhodu předplatitele.

V rámci [portál odběratele Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), bude pravděpodobně možné přidat **alternativní identity** – kromě Identita použitá během aktivace. V současné době nám umožňují přidání alternativní identity, pokud jste použili účet Microsoft předplatné aktivujete. Tento způsob, jak můžete také přidat pracovní nebo školní účet (který používáte při přihlašování sady Visual Studio, Office 365 nebo firemní nebo školní sítě), což umožňuje přístup k služby VSTS pomocí účtu osobní i pracovní nebo školní účet.

## <a name="add-an-alternate-account-to-your-visual-studio-subscription"></a>Přidání alternativního účtu do vašeho předplatného sady Visual Studio

Přidání alternativního účtu k odběru sady Visual Studio umožňuje přístup k odběru výhod, jako Visual Studio Team Services (VSTS) a Azure, s jinou identitou, než která je přiřazená předplatné. V minulosti tato funkce byla k dispozici pouze v případě, že vaše předplatné Visual Studio (VS) byl přiřazen k účet Microsoft (MSA). Jsme rozšířili tuto funkci pro pracovní nebo školní účty v Azure Active Directory (Azure AD).

To neposkytuje kopii odběru pro jiný účet; poskytuje pouze dvě výhody pomocí alternativního účtu přístup.

Pro všechna předplatná můžete přidat "pracovní nebo školní účet", abyste je mohli používat tento účet s vaší výhody, které vyžadují přihlašovací údaje (VS IDE, služby VSTS a Azure).

### <a name="prerequisites"></a>Požadavky

* [Služby VSTS projektu správce kolekce nebo oprávnění vlastníka účtu](https://docs.microsoft.com/en-us/vsts/accounts/faq-add-delete-users#find-owner).

* Chcete-li použít alternativní účet, musí obsahovat vaše předplatné spojené s vaším účtem, Visual Studio Team Services nebo Microsoft Azure.

> [!Note]
> Budete můžete nadále používat vaše předplatné výhody s vaší alternativní ID, ale vaše předplatné je stále spojena se původní účet.

### <a name="add-the-alternate-account"></a>Přidání alternativního účtu

1. Přihlaste se k sadě Visual Studio pomocí účtu Microsoft (https://{youraccount}.visualstudio.com).

2. Přejděte na **odběry**.

  ![Přidání alternativního účtu – přejděte na předplatná v sadě VS](_img/vs-alternate-identity/my-vs-subscriptions.png)

3. Zvolte **přidání alternativního účtu**.

  ![Zvolte přidání alternativního účtu ](_img/vs-alternate-identity/choose-add-alternate-account.png)

4. Přidáte pracovní nebo školní účet.

  ![Přidat pracovní nebo školní účet](_img/vs-alternate-identity/enter-alternate-account-my-visual-studio-com-portal.png)

5. Použijte pracovní nebo školní účet pro přihlášení k sadě Visual Studio (https://{youraccount}.visualstudio.com).

  ![Použijte svůj pracovní nebo školní účet](_img/vs-alternate-identity/sign-in-with-alternate-account.png)

  Vaše alternativní účet je přidán do sady Visual Studio odběru, což obou identity využívat výhody předplatného, které vyžadují, abyste se přihlaste pomocí alternativního účtu (IDE, služby VSTS a Azure).

Další informace o přidání alternativního účtu najdete v tématu [Moje Visual Studio – nejčastější dotazy](https://www.visualstudio.com/my/myvsfaq#alternate) stránky.

## <a name="faq"></a>Nejčastější dotazy

### <a name="q--why-doesnt-vsts-recognize-me-as-a-visual-studio-subscriber"></a>Otázka: Proč služby VSTS nerozpoznal mi jako odběratel Visual Studio?
A: služby VSTS by měl automaticky rozpoznat vaše předplatné při přihlášení pomocí vaší primární nebo alternativní identity. Pokud ne, můžete zkusit několik věcí:

* Zkontrolujte, že máte aktivní předplatné sady Visual Studio, [zahrnuje služby VSTS jako výhody](vs-vsts.md).

* Potvrďte, že používáte přihlášení nebo identitou, která je buď primární nebo alternativní identitu pro vaše předplatné sady Visual Studio.

* Přejděte [portál odběratele Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs) alespoň jednou před přihlášení do služby VSTS.

Pokud služby VSTS stále nerozpoznal vaše předplatné [obraťte se na podporu](https://www.visualstudio.com/team-services/support/)
