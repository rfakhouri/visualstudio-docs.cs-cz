---
title: Připojení k portálu pro správu předplatných sady Visual Studio po dokončení migrace
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 07/12/2018
ms.topic: conceptual
description: Zjistěte, jak úspěšně připojit vaše organizace pro předplatná sady Visual Studio po migraci na portál pro správu.
searchscope: VS Subscription
ms.openlocfilehash: 188842272f7e4ee102829f961b29b4d5ffbf70dc
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58154176"
---
# <a name="onboard-to-the-visual-studio-subscriptions-administration-portal-after-your-organization-is-migrated"></a>Připojení k portálu správy předplatných Visual Studio po vaší organizace migrována

Je-li spravovat předplatná sady Visual Studio v Microsoft svazek licencování Service Center (VLSC) a jste nedávno navštívili lokalitu pro správu předplatných, si všimnete, že Správa předplatného už nejsou k dispozici na webu VLSC. Váš proces ke správě předplatných byste se podívat takto:
> [!div class="mx-imgBorder"]
> ![Snímek obrazovky s Microsoft VLSC, na kartě předplatná zvýrazněnou](_img/post-migration-onboarding/vlsc-subscriptions.png)

Předplatná se teď spravují prostřednictvím nového portálu názvem portál pro správu předplatných Visual Studio. Standardně primární nebo informační kontakt pro multilicenční smlouvou, vaše organizace dokončení tohoto procesu. Pokud ne, tyto informace vám získat přístup ke správě přihlášení k odběru.

Může dojít, jeden z několika situacích:

1. [Primární kontakt nedokončil proces registrace.](#onboarding-not-completed-by-primary-contact)
2. [Primární kontakt registrace dokončena, ale neměli vás přidal jako správce. Vaše přihlašovací údaje byly uvedeny na webu VLSC.](#primary-contact-did-not-provide-you-administrator-access)
3. [Primární kontakt registrace dokončena, ale neměli vás přidal jako správce. Vaše přihlašovací údaje nejsou uvedené ve VLSC.](#Your-credentials-were-not-listed-in-VLSC-prior-to-migration)

<sup>1</sup> Pokud jsou primární nebo se obraťte se na oznámení a nedokončil proces registrace, budete muset podle kroků v scénář č. 1, aby bylo možné nastavit svou organizaci.

Následující oddíly poskytují další podrobnosti o každé z těchto scénářů.

## <a name="onboarding-not-completed-by-primary-contact"></a>Registrace nebyla dokončena ve primárního kontaktu

Pokud adresu primárního kontaktu se nepodařilo dokončit registraci prostředí, zobrazí se následující obrazovka. Pokud máte přístup k [Volume Licensing Service Center (VLSC)](https://www.microsoft.com/Licensing/servicecenter/default.aspx), můžete to provést a získat přístup ke správě předplatných. Vaše organizace budete potřebovat [veřejné zákaznické číslo (PCN)](find-pcn.md), kterou lze nalézt ve VLSC.

V poli PCN, zadejte [PCN](find-pcn.md)a vyberte **odeslat e-mailová pozvánka**.
> [!div class="mx-imgBorder"]
> ![Snímek obrazovky portálu pro správu předplatných sady Visual Studio](_img/post-migration-onboarding/send-invitation.png)

Obdržíte e-mail s odkazem na jedinečný dokončit proces zařazení do systému. Klikněte na odkaz v e-mailu, přihlaste se pomocí e-mailovou adresu a ještě jednou zadejte PCN. Jedinečného odkazu v e-mailu je, co vám umožňuje získat přístup k portálu správy předplatných Visual Studio. Můžete pak přístup k a spravovat odběry.
> [!div class="mx-imgBorder"]
> ![Snímek obrazovky na úspěch oznámení](_img/post-migration-onboarding/email-success.png)

## <a name="primary-contact-did-not-provide-you-administrator-access"></a>Primární kontakt je neposkytl přístup správce

Pokud váš primární kontakt dokončit proces zařazení do systému a vaše přihlašovací údaje se dříve nacházely ve VLSC, ale neposkytli jste adresu primárního kontaktu s přístupem, se zobrazí následující oznámení. Staňte se správcem, obraťte se na jednu ze supersprávců, kteří jsou vaší organizace uvedené v oznámení.
> [!div class="mx-imgBorder"]
> ![Snímek obrazovky sady Visual Studio portál pro správu předplatných, seznam supersprávců, kteří jsou](_img/post-migration-onboarding/admin-list.png)

## <a name="your-credentials-were-not-listed-in-vlsc-prior-to-migration"></a>Vaše přihlašovací údaje nejsou uvedení ve VLSC před migrací

Pokud váš primární kontakt dokončení registrace, ale nepřidali jste jako uživatel a vaše přihlašovací údaje nebyly dříve uvedené ve VLSC, se zobrazí následující oznámení. Kontaktujte vašeho [primární kontakt](find-primary-contact.md) získat přístup k portálu.
> [!div class="mx-imgBorder"]
> ![Snímek obrazovky sady Visual Studio portál pro správu předplatných, s oznámením "nelze najít je"](_img/post-migration-onboarding/cant-find-you.png)