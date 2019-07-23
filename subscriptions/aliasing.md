---
title: Přihlášení k předplatným sady Visual Studio může při použití aliasů selhat. | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/19/2019
ms.topic: conceptual
description: Přihlášení se nemusí zdařit, pokud se používají aliasy nebo popisné názvy.
ms.openlocfilehash: 392b86699b1116f45ca75df3b611fff6a2aebc62
ms.sourcegitcommit: 485881e6ba872c7b28a7b17ceaede845e5bea4fe
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/22/2019
ms.locfileid: "68378021"
---
# <a name="signing-in-to-visual-studio-subscriptions-may-fail-when-using-aliases"></a>Přihlášení k předplatným sady Visual Studio může při použití aliasů selhat.
V závislosti na typu účtu použitého k přihlášení nemusí být dostupné odběry při přihlášení ke [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs)správnému zobrazení. Jednou z možných příčin je použití "aliasů" nebo "popisných názvů" místo přihlašovací identity, ke které je předplatné přiřazeno. Tento název se nazývá "aliasing".

## <a name="what-is-aliasing"></a>Co je aliasing?
Pojem "aliasing" odkazuje na uživatele, kteří mají různé identity pro přihlášení k Windows (nebo službě Active Directory) a pro přístup k e-mailu.

Aliasing se může vyskytnout, když má společnost Microsoft Online Service pro své adresáře, jakoJohnD@contoso.comje, ale uživatelé mají přístup k e-mailovým účtům pomocí aliasů nebo popisných názvů,John.Doe@contoso.comjako je například. Pro mnoho zákazníků, kteří spravují své odběry prostřednictvím služby Volume Licensing Service Center (VLSC), může dojít k neúspěšnému přihlášení, protože zadaná e-mailová adresa (John.Doe@contoso.com') neodpovídá adrese adresářeJohnD@contoso.com(' '. ) vyžadované k úspěšnému ověření prostřednictvím možnosti pracovní nebo školní účet.

## <a name="as-an-administrator-what-options-do-i-have"></a>Jaké možnosti mám k dispozici jako správce?
Jako správce máte k dispozici dvě možnosti, jak zajistit, aby vaši předplatitelé měli úspěšné prostředí pro [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs)přihlášení.
- První možností (doporučeno) je použít účet adresáře jako přiřazenou adresu na portálu Volume Licensing Service Center (VLSC). Další podrobnosti najdete v části [přiřazení předplatitelů k účtu adresáře](#assigning-subscribers-to-a-directory-account) v tomto článku.
- Druhá možnost (méně bezpečná) znamená, že předplatitelům umožní přidružit svou pracovní nebo školní e-mailovou adresu k osobnímu účtu (označuje se také jako Účet Microsoft nebo MSA). Další podrobnosti najdete v části [definování pracovního nebo školního účtu jako osobního účtu](#defining-a-work-or-school-account-as-a-personal-account) v tomto článku.

> [!NOTE]
> Jakmile se vaše společnost migruje na nový [portál pro správu](https://manage.visualstudio.com)předplatných sady Visual Studio, budete moct využít nové prostředí pro správu, které umožní poskytovat adresář i e-mailové adresy jako součást předplatitele. profilu. Přečtěte si další informace o [migraci](https://support.microsoft.com/help/4013930/visual-studio-subscriptions-administrator-migration-details).

## <a name="assigning-subscribers-to-a-directory-account"></a>Přiřazení předplatitelů k účtu adresáře
Ve všech případech musí správce předplatného v rámci multilicenčního programu VLSC (Volume Licensing Service Center) používat adresu adresáře pro nové předplatitele nebo aktualizovat e-mailovou adresu pro stávající předplatitele. Je důležité si uvědomit, že použití adresy adresáře bude znamenat, že noví předplatitelé nebudou dostávat uvítací E-mail a správce bude muset upozornit předplatitele, že k nim byl přiřazen odběr. Až budete postupovat podle následujících kroků, můžete také používat e-mailovou [šablonu](#notifying-your-subscribers-with-directory-addresses) k upozorňování předplatitelů a pomáhat jim prostřednictvím procesu přihlašování.

### <a name="adding-new-subscribers"></a>Přidávání nových předplatitelů
Pokud chcete přidat nového předplatitele s adresářovým účtem, postupujte prosím podle těchto kroků.

1. Přejděte na web [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) a přihlaste se.
2. Na stránce Správce VLSC klikněte na **odběry** a pak na předplatná sady **Visual Studio**.

    > [!div class="mx-imgBorder"]
    > ![Nabídka odběry](_img//vlsc/vlsc-subscriptions.png)

3. Klikněte na **číslo smlouvy** přidružené k Visual Studio Subscription.

    > [!div class="mx-imgBorder"]
    > ![Vybrat smlouvu](_img/vlsc/vlsc-agreement.png)

4. Klikněte na **přiřadit předplatné**.
5. Vyberte požadovanou **úroveň**předplatného.
6. Ověřte, že máte k dispozici odběry k přiřazení, a klikněte na tlačítko **Další**.
7. Do pole e-mailová adresa zadejte podrobnosti předplatitele a adresu adresáře a klikněte na **Další**.
8. Ověřte informace o odběrateli a klikněte na tlačítko **Dokončit**.
9. Informujte předplatitele o zřízení jejich předplatného pomocí níže uvedené [šablony](#notifying-your-subscribers-with-directory-addresses).

### <a name="updating-an-existing-subscriber"></a>Aktualizace existujícího předplatitele
Chcete-li aktualizovat stávajícího předplatitele pomocí účet adresáře, postupujte prosím podle následujících pokynů.

1. Přejděte na web [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) a přihlaste se.
2. Na stránkách správce VLSC klikněte na **odběry** a pak na předplatná sady **Visual Studio**.
3. Klikněte na **číslo smlouvy** přidružené k Visual Studio Subscription.
4. Klikněte na **šipku dolů** na panelu hledání.
5. Vyhledejte předplatitele pomocí pole e-mailová adresa.
6. V seznamu výsledků klikněte na **poslední jméno** předplatitele.
7. Klikněte na **Upravit**.
8. Změňte pole e-mailové adresy na požadovanou adresu adresáře a klikněte na **Uložit**.
9. Informujte předplatitele o zřízení jejich předplatného pomocí e-mailové šablony.

### <a name="notifying-your-subscribers-with-directory-addresses"></a>Informování o předplatitelích s adresami adresáře
Vzhledem k tomu, že uvítací E-mail nebude úspěšně dostupný vašemu předplatiteli, zkopírujte a vložte níže uvedenou zprávu do e-mailu a pošlete ji předplatiteli. Nahraďte% WORD% příslušnými informacemi pro každého předplatitele.

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

## <a name="defining-a-work-or-school-account-as-a-personal-account"></a>Definování pracovního nebo školního účtu jako osobního účtu
Pokud chcete přidat nového uživatele nebo aktualizovat e-mailovou adresu uživatele na portálu Volume Licensing Service Center (VLSC), postupujte podle pokynů popsaných v části [přiřazení předplatitelů k účtu adresáře](#assigning-subscribers-to-a-directory-account) .  V případech, kdy je e-mailová adresa rozpoznána v adresáři, bude uživatel muset projít procesem vytvoření nového účtu pro definování e-mailové adresy jako osobního účtu.  Pro krátkou dobu tým předplatných sady Visual Studio zabezpečuje výjimku ze zásad identity definovaných níže, ale poskytujeme možnostem, které jsou nezbytné k odebrání této zásady.

> [!WARNING]
> Microsoft nedoporučuje kombinaci "pracovních nebo školních" identit s "osobními" identitami.  Tato akce způsobí, že organizace ztratí vlastnictví a kontrolu nad účtem a zaměstnanec může i nadále přistupovat k určitým produktům nebo službám, i když opustí společnost.  

### <a name="defining-an-email-address-as-a-personal-account"></a>Definování e-mailové adresy jako osobního účtu
Po přiřazení předplatného k předplatiteli obdrží e-mail s žádostí, aby [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) mohli využít výhody jejich předplatného.  Při pokusu o přihlášení se Visual Studio Subscription přihlášení nezdaří s chybou informující o tom, že účet není známý.  Než se přihlásíte [https://my.visualstudio.com](https://my.visualstudio.com?wt.mc_id=o~msft~docs) k prostředí, požádejte předplatitele, aby postupoval podle těchto pokynů.  V případě potřeby můžete tuto [šablonu](#notifying-your-subscribers-using-personal-accounts) použít k informování předplatitele po přiřazení předplatného.

1. Přejděte na https://my.visualstudio.com a klikněte na **vytvořit novou účet Microsoft**.

2. Vyplňte pole:
   - Zadejte e-mailovou adresu, na kterou se v Someone@example.com boxu dostal uvítací e-mail.
   - Vytvoření hesla
   - Volba nastavení propagační akce
   - Klikněte na **Další** .

3. Dokončete kroky ověření a klikněte na tlačítko **Další**.

4. Noví uživatelé možná budou muset dokončit profil sady Visual Studio.

5. Předplatné a výhody by teď mělo být viditelné.

### <a name="notifying-your-subscribers-using-personal-accounts"></a>Informování o předplatitelích pomocí osobních účtů
Ve scénáři uvedeném výše vám předplatitel obdrží "uvítací E-mail", ale kvůli aliasům by se mu nemohli přihlásit.  Následující text můžete použít k informování předplatitele výše uvedeného postupu a Doporučené možnosti podpory v případě potřeby.  Nahraďte% WORD% příslušnými informacemi pro každého předplatitele.

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
