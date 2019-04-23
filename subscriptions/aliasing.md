---
title: Přihlášení k předplatná sady Visual Studio může selhat při použití aliasy | Dokumentace Microsoftu
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/02/2018
ms.topic: conceptual
description: Přihlášení může selhat, pokud se používají aliasy nebo popisné názvy
searchscope: VS Subscription
ms.openlocfilehash: ac3f9df365e0b7924b615c2ae8cbb70d93d04948
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60041382"
---
# <a name="signing-in-to-visual-studio-subscriptions-may-fail-when-using-aliases"></a>Přihlášení k předplatná sady Visual Studio může selhat, pokud aliasy using

V závislosti na typu účtu, použili pro přihlášení, nemusí být správně zobrazovat dostupná předplatná při přihlašování k [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs). Jednou z možných příčin je použití "aliasy" nebo "popisné názvy" místo identity přihlášení ke kterému je přiřazené předplatné. Tomu se říká "aliasy".

## <a name="what-is-aliasing"></a>Co je aliasing?

Pojem "aliasy" představuje uživatelé mají různé identity pro přihlášení k Windows (nebo službě Active Directory) a pro přístup k e-mailu.

Aliasy může dojít, když má společnost Microsoft Online Service pro adresář přihlášení, jako je třeba JohnD@contoso.com, ale uživatelé přístup k jejich e-mailové účty pomocí aliasů nebo popisné názvy, například John.Doe@contoso.com. Pro mnoho zákazníků, kteří spravují svá předplatná prostřednictvím na svazek licencování Service Center (VLSC), může dojít k úspěšné prostředí přihlásit jako e-mailovou adresu za předpokladu (John.Doe@contoso.com) neodpovídá adrese adresáře (JohnD@contoso.com) požadované pro úspěšné ověření prostřednictvím možnosti "Pracovní nebo školní účet".

## <a name="as-an-administrator-what-options-do-i-have"></a>Jako správce jaké jsou možnosti?

Jako správce, existují dvě možnosti, vaši předplatitelé měli prostředí úspěšné přihlášení [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs).
- První možnost (doporučeno), je využít adresář účtu jako přiřazenou adresu v Volume Licensing Service Center (VLSC). Odkazovat na [přiřazení předplatitele adresář účtu](#assigning-subscribers-to-a-directory-account) části v tomto článku najdete další podrobnosti.
- (Méně bezpečné), druhou možností je povolit vaši předplatitelé (označovaný také jako přidružení e-mailová adresa "Pracovní nebo školní" na "Osobní" účet Microsoft Account or MSA). Odkazovat na [definování pracovního nebo školního účtu jako osobní účet](#defining-a-work-or-school-account-as-a-personal-account) části v tomto článku najdete další podrobnosti.

> [!NOTE]
> Jakmile se vaše společnost je migrovat na nová předplatná sady Visual Studio [portálu pro správu](https://manage.visualstudio.com), budete moci využít výhod tohoto nového prostředí správy, což umožní adresáře a e-mailové adresy poskytované v rámci profil účastníka. Další informace o [migrace](https://support.microsoft.com/help/4013930/visual-studio-subscriptions-administrator-migration-details).

## <a name="as-a-subscriber-what-options-do-i-have"></a>Jako předplatitel jaké jsou možnosti?

Z hlediska předplatitele je důležité pro první práci se svým správcem o konfigurace identity vaší společnosti. V případě potřeby správce pravděpodobně nutné aktualizovat nastavení vašeho účtu ze svého portálu pro správu nebo budete muset vytvořit účet Microsoft (MSA) pomocí podnikové e-mailovou adresu. Před přepnutím kroky k vytvoření MSA, mluví se svým správcem o všech zásad nebo problémy s provedením této akce. Odkazovat na [definování pracovního nebo školního účtu jako osobní účet](#defining-a-work-or-school-account-as-a-personal-account) části v tomto článku najdete další podrobnosti.

## <a name="assigning-subscribers-to-a-directory-account"></a>Přiřadit předplatitele adresář účtu

Ve všech případech se správce předplatného v rámci Volume Licensing Service Center (VLSC) musíte použít adresu adresáře pro nové předplatitele nebo předplatitelům "existující" aktualizaci e-mailovou adresu. Je důležité si uvědomit, že pomocí adresa adresáře bude znamenat žádné nové předplatitele neobdrží Uvítacího e-mailu a správce muset informovat odběratele, které jim byly přiřazeny předplatné. Po následujícím níže uvedené kroky, také můžete použít e-mailu [šablony](#notifying-your-subscribers-with-directory-addresses) oznámit vaši předplatitelé a pomoci prostřednictvím procesu přihlášení.

### <a name="adding-new-subscribers"></a>Přidání nové předplatitele

Postupujte podle těchto kroků pro přidání nového odběratele s účtem služby adresáře.

1. Přejděte [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) a přihlaste se.
2. Na stránce Správce VLSC klikněte na tlačítko **předplatná** a potom **předplatných sady Visual Studio**.

    > [!div class="mx-imgBorder"]
    > ![Nabídka předplatného](_img//vlsc/vlsc-subscriptions.png)

3. Klikněte na tlačítko **číslo smlouvy** přidružený k předplatnému sady Visual Studio.

    > [!div class="mx-imgBorder"]
    > ![Vyberte smlouvy](_img/vlsc/vlsc-agreement.png)

4. Klikněte na tlačítko **přiřazení předplatného**.
5. Vyberte požadovaný **úroveň předplatného**.
6. Ověření máte předplatné k dispozici chcete přiřadit a klikněte na tlačítko **Další**.
7. Zadejte podrobné údaje o předplatitelích a adresu adresáře do pole e-mailovou adresu a klikněte na tlačítko **Další**.
8. Ověřte informace o odběrateli a klikněte na **Dokončit**.
9. Oznámení odběrateli, že svoje předplatné se zřizují pomocí níže [šablony](#notifying-your-subscribers-with-directory-addresses).

### <a name="updating-an-existing-subscriber"></a>Aktualizace stávající předplatitel

Postupujte prosím podle následujících kroků aktualizujte stávající předplatitel s účtem služby adresáře.

1. Přejděte [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) a přihlaste se.
2. Na stránkách správce VLSC klikněte na **předplatná** a potom **předplatných sady Visual Studio**.
3. Klikněte na tlačítko **číslo smlouvy** přidružený k předplatnému sady Visual Studio.
4. Klikněte na tlačítko **šipka dolů** na vyhledávacím panelu.
5. Vyhledejte předplatitele. pomocí pole "E-mailová adresa".
6. V seznamu výsledků klepněte **příjmení** odběratele.
7. Klikněte na tlačítko **upravit**.
8. Změňte pole e-mailovou adresu na adresu požadovaném adresáři a klikněte na tlačítko **Uložit**.
9. Oznámení odběrateli, že svoje předplatné se zřizují pomocí následující e-mailové šablony.

### <a name="notifying-your-subscribers-with-directory-addresses"></a>Upozornění vašim předplatitelům s adresami adresáře

Protože Uvítacího e-mailu úspěšně nedostanou vaše odběratele, zkopírujte a vložte níže zpráv do e-mailu a odeslat do vašich odběratele. Nahraďte odpovídajícími informacemi pro každý předplatitel % slova.

```
----------- Copy Below (Ctrl+C) -----------

Hello %SUBSCRIBER NAME%

You have been assigned a Visual Studio subscription. Please visit https://my.visualstudio.com, and log in with your %DIRECTORY ADDRESS% address to activate and access your subscription.

If you’re having trouble, please contact the support team (https://visualstudio.microsoft.com/subscriptions/support/).

At the bottom of the page, select the following:
   - Accounts, Subscriptions, and Billing Support
   - From Issue, choose Subscription sign in support
   - Choose the appropriate Country
   - Select the desired Assisted Support option

----------- End Copy -----------
```

## <a name="defining-a-work-or-school-account-as-a-personal-account"></a>Definování pracovního nebo školního účtu jako osobní účet

Prosím využít pokynů v tématu [přiřazení předplatitele adresář účtu](#assigning-subscribers-to-a-directory-account) části k přidání nového uživatele nebo aktualizaci e-mailovou adresu uživatele v rámci Volume Licensing Service Center (VLSC).  V případech, kde není rozpoznána e-mailovou adresu adresáře bude uživatel muset projít procesem vytvoření nového účtu k definování e-mailovou adresu jako osobní účet.  Pro krátkodobou tým předplatných sady Visual Studio má zabezpečené výjimku z níže definovanou zásadu identity, ale můžeme společností investuje do funkce potřeba odebrat tyto zásady.

> [!WARNING]
> Microsoft nedoporučuje kombinace identity "Pracovní nebo školní" s "Osobní" identit.  Tato akce způsobí, že organizace ke ztrátě vlastnictví a kontrolu nad účet a zaměstnanci měli dál přístup k určité produkty nebo služby, dokonce i potom, co odejdete společnosti.  Najdete v tomto [blogový příspěvek](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/15/cleaning-up-the-azure-ad-and-microsoft-account-overlap/), od týmu Microsoft Identity, další informace.

### <a name="defining-an-email-address-as-a-personal-account"></a>Definování e-mailovou adresu jako osobní účet

Po přiřazení předplatného je k odběrateli, dostanou e-mail s požadavkem na web [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs) výhod svých předplatitelských výhod.  Při pokusu o přihlášení, přihlášení předplatné sady Visual Studio dojde k selhání s chyba oznamující, že účet nebyl rozpoznán.  Před přihlášením na stránce [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs) prostředí, požádejte vašeho odběratele postupujte podle následujících pokynů.  Pokud nezbytné, může být využit [šablony](#notifying-your-subscribers-using-personal-accounts) oznámit vaše odběratele po přiřazení předplatného.

1. Přejděte do https://my.visualstudio.coma klikněte na tlačítko **vytvořit nový účet Microsoft**.

2. Vyplňte pole:
   - Zadejte e-mailovou adresu, který obdržel Uvítacího e-mailu v Someone@example.com pole
   - Vytvořit heslo
   - Zvolte nastavení propagační akce
   - Klikněte na tlačítko **další**

3. Proveďte kroky ověření a klikněte na tlačítko **Další**.

4. Noví uživatelé muset vyplnit profil pro Visual Studio.

5. Předplatné a výhody by měla nyní být viditelné.

### <a name="notifying-your-subscribers-using-personal-accounts"></a>Upozornění vašim předplatitelům s využitím osobní účty

Ve scénáři uvedeném výše vaši předplatitelé dostanou "Uvítací E-mail", ale kvůli aliasy, které se můžou vyskytnout, že se že nebudou moct přihlásit.  Můžete použít následující text, který má upozornit vaši předplatitelé výše uvedené kroky a doporučuje možnosti podpory v případě potřeby.  Nahraďte odpovídajícími informacemi pro každý předplatitel % slova.

```
----------- Copy Below (Ctrl+C) -----------

Hello %SUBSCRIBER NAME%

You have been assigned a Visual Studio subscription, and may have been directed to log into https://my.visualstudio.com based on your Welcome email.  While this is the correct website for consuming benefits, our organization requires you to take a few extra steps before you can access the site.  Please follow the below instructions to help you create a “Microsoft Account” that is tied to our corporate email address.  Once these steps are completed, you will use your email address to access the Subscription benefits.
1. Visit https://my.visualstudio.com

2. Click Create new Microsoft Account on the right hand side

3. Complete the Form:
   - Use your corporate email address in the someone@example.com box
   - Enter a password
   - Select your promotional preference
   - Click Next

4. Complete the account validation steps

5. If necessary, complete the Visual Studio profile

6. You should now see your benefits

Note:  When visiting https://my.visualstudio.com in the future, you may be prompted to select which account you’d like to use (e.g. “Work or School Account” or “Personal Account”).  After following the steps above, you will need to leverage the “Personal Account” option.

If you’re having trouble, please contact the support team (https://visualstudio.microsoft.com/subscriptions/support/).

At the bottom of the page, select the following:
   - Accounts, Subscriptions, and Billing Support
   - From Issue, choose Subscription sign in support
   - Choose the appropriate Country
   - Select the desired Assisted Support option

----------- End Copy -----------
```
