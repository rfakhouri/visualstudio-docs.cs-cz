---
title: Přihlášení k sadě Visual Studio odběry může selhat, pokud používáte aliasy | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/02/2018
ms.topic: Get-Started-Article
description: Přihlášení může selhat v případě aliasy nebo popisné názvy se používají.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 765862efcd3b83be2d52767dbc81570da2e8f9d6
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34477649"
---
# <a name="signing-in-to-visual-studio-subscriptions-may-fail-when-using-aliases"></a>Přihlášení k sadě Visual Studio odběry může selhat, pokud používáte aliasy

V závislosti na typu účet použili k přihlášení, dostupných předplatných, se nemusí zobrazit správně při přihlašování k [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs). Jedna z možných příčin je použití "aliases" nebo "popisné názvy" místo identity přihlášení ke kterému se předplatné přiřadí. Tomu se říká "aliasy". 

## <a name="what-is-aliasing"></a>Co je aliasy?

Termín "aliasy" odkazuje na uživatelích, kteří mají různé identity pro přihlášení k systému Windows (nebo služby Active Directory) a přístup k e-mailu.

Aliasy můžete došlo, pokud má společnost Microsoft Online Service pro jejich directory přihlášení, jako je třeba JohnD@contoso.com, ale uživatelé přístup k jejich e-mailové účty pomocí aliasy nebo popisných názvů, jako třeba John.Doe@contoso.com.  Pro mnoho zákazníků, kteří spravují předplatné prostřednictvím webu Volume Licensing Service Center (VLSC), může být výsledkem prostředí neúspěšných přihlášení jako e-mailová adresa zadaná (John.Doe@contoso.com) neodpovídá adrese adresáře (JohnD@contoso.com) vyžaduje se pro úspěšné ověření pomocí možnosti "Pracovní nebo školní účet".

## <a name="as-an-administrator-what-options-do-i-have"></a>Jako správce Jaké mám možnosti?

Jako správce, existují dvě možnosti pro zajištění vaší Odběratelé, kteří mají úspěšné možností přihlašování na [ https://my.visualstudio.com ](https://my.visualstudio.com?wt.mc_id=o~msft~docs). 
- První možnost (doporučeno), je využít účet directory jako přiřazenou adresu v webu Volume Licensing Service Center (VLSC). Odkazovat na [přiřazení Odběratelé účet Directory](#assigning-subscribers-to-a-directory-account) v tomto článku Další podrobnosti.
- Druhá možnost (méně bezpečné), je umožnit zákazníků a přidružit e-mailové adresy "Pracovní nebo školní" na "Osobní" účet (také známa jako Účet Microsoft nebo účtu spravované služby). Odkazovat na [definování pracovní nebo školní účet jako účet osobní ](#defining-a-work-or-school-account-as-a-personal-account ) v tomto článku Další podrobnosti.

> [!NOTE]
> Jakmile je vaše společnost migrovat na nové odběry v sadě Visual Studio [portálu pro správu](https://manage.visualstudio.com), bude možné využívat nové prostředí správy, která umožňuje adresář a e-mailové adresy poskytované v rámci profil odběratele.  Další informace o [migrace](https://support.microsoft.com/help/4013930/visual-studio-subscriptions-administrator-migration-details).

## <a name="as-a-subscriber-what-options-do-i-have"></a>Jako odběratel Jaké mám možnosti?

Z hlediska odběratele je důležité první spolupráci se správcem zjistit konfiguraci identity vaší společnosti.  V případě potřeby správce pravděpodobně nutné aktualizovat nastavení svého účtu z portálu pro správu, nebo budete muset vytvořit Microsoft účtu (MSA) pomocí vaší firemní e-mailovou adresu.  Před provedením kroků pro vytvoření účet spravované služby, řeči se na správce týkající se všechny zásady nebo problémy s provedením této akce.  Odkazovat na [definování pracovní nebo školní účet jako účet osobní ](#defining-a-work-or-school-account-as-a-personal-account ) v tomto článku Další podrobnosti.  

## <a name="assigning-subscribers-to-a-directory-account"></a>Přiřazení odběratele, kteří mají účet adresáře 

Ve všech případech nutné odběr Manager v rámci webu Volume Licensing Service Center (VLSC) použijte adresu adresář pro nové odběratele, nebo aktualizovat e-mailovou adresu pro "existující" odběratele.  Je důležité si uvědomit, že pomocí adresy directory znamená žádné nové odběratele neobdrží Uvítacího e-mailu a správce bude muset oznámení odběrateli, který jim byl přiřazen předplatné.  Po následující níže uvedených pokynů, prosím také klidně používat e-mailu [šablony](#notifying-your-subscribers-with-directory-addresses) chcete upozornit vaší odběratele a pomáhá jim prostřednictvím procesu přihlášení.

### <a name="adding-new-subscribers"></a>Přidání nové odběratele
Postupujte podle těchto kroků pro přidání nové odběratele s účtem adresáře.

1. Přejděte [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) a přihlaste se.
2. Na stránce VLSC správce, klikněte na tlačítko **odběry** a potom **Visual Studio odběry**.

    <img alt="Subscriptions menu" src="_img//vlsc/vlsc-subscriptions.png" style="border: 1px solid #CCCCCC" />

3. Klikněte **číslo smlouvy** přidruženou k odběru Visual Studio.

    <img alt="Select agreement" src="_img/vlsc/vlsc-agreement.png" style="border: 1px solid #CCCCCC" />

4. Klikněte na tlačítko **přiřadit předplatné**.

    <img alt="Assign subscription" src="_img/vlsc/vlsc-assign.png" style="border: 1px solid #CCCCCC" />


5. Vyberte požadovanou **úrovni předplatného**.

    <img alt="Subscription level" src="_img/vlsc/vlsc-subscription-level.png" style="border: 1px solid #CCCCCC" /> 

6. Ověření je nutné přiřadit, a klikněte na dostupných předplatných **Další**.
7.  Zadejte podrobnosti o odběrateli a directory adresu v poli e-mailovou adresu a klikněte na tlačítko **Další**.

    <img alt="Email address" src="_img/vlsc/vlsc-email-address.png" style="border: 1px solid #CCCCCC" /> 
        
8. Ověřte informace o odběrateli a klikněte na tlačítko **Dokončit**.

9. Oznámení odběrateli svoje předplatné se zřizují pomocí níže [šablony](#notifying-your-subscribers-with-directory-addresses).

### <a name="updating-an-existing-subscriber"></a>Aktualizace stávajícího odběratele
Postupujte níže uvedených pokynů k aktualizaci stávajícího odběratele s účtem adresáře.

1. Přejděte [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx) (VLSC) a přihlaste se.

2. Ze stránky VLSC správce, klikněte na tlačítko **odběry** a potom **Visual Studio odběry**.

3. Klikněte **číslo smlouvy** přidruženou k odběru Visual Studio.

4. Klikněte **šipka dolů** v panelu vyhledávání.

5. Vyhledávání pro odběratele pomocí pole "E-mailová adresa".

6. V seznamu výsledků klepněte **příjmení** odběratele.

7. Klikněte na tlačítko **upravit**.

8. Změňte pole e-mailovou adresu na adresu požadovanou adresář a klikněte na tlačítko **Uložit**.

9. Oznámení odběrateli svoje předplatné se zřizují pomocí níže šablona e-mailu.

### <a name="notifying-your-subscribers-with-directory-addresses"></a>Upozornění odběratelů adresy adresáře
Vzhledem k tomu, že Uvítacího e-mailu nebudou úspěšně dostat vaší odběratele, zkopírujte a vložte pod zprávu do e-mailu a odeslat do vaší odběratele. Nahraďte WORD % příslušné informace pro každý odběratele.

---Kopie níže (Ctrl + C),

Hello % odběratele NAME %

Jste byli přiřazeni předplatné sady Visual Studio.  Navštivte https://my.visualstudio.coma přihlaste se pomocí % % adresu umístění adresáře pro aktivaci a přístup k předplatnému. 

Pokud máte problémy, kontaktujte prosím tým podpory (https://www.visualstudio.com/subscriptions/support/).

V dolní části stránky vyberte následující položky:
   - Účty, odběry a podpory fakturace
   - Z problém zvolíte předplatné přihlašovací podpory
   - Vyberte příslušnou zemi
   - Vyberte požadovanou možnost odbornou pomoc

---Konec zkopírování---



## <a name="defining-a-work-or-school-account-as-a-personal-account"></a>Definování pracovní nebo školní účet jako účet osobní 
Prosím využít podle pokynů v tématu [přiřazení Odběratelé účet Directory](#assigning-subscribers-to-a-directory-account) části přidat nového uživatele nebo aktualizovat e-mailovou adresu uživatele v rámci webu Volume Licensing Service Center (VLSC).  V případech, kde není v adresáři rozpoznány e-mailovou adresu uživatel bude muset krok procesu vytvoření nového účtu zadat e-mailovou adresu jako osobní účet.  Pro krátkodobou odběry Visual Studio team má zabezpečené výjimku ze zásad identity definovaná níže, ale jsme se začne investovat možnosti potřeba odebrat tuto zásadu.

> [!WARNING]
> Společnost Microsoft nedoporučuje kombinace identity "Pracovní nebo školní" s "Osobní" identity.  Tato akce způsobí ztrátu vlastnictví a řízení účtu organizace a jednotlivých zaměstnanců může získat přístup k určité produkty nebo služby, i po opouští společnost.  Prosím tento odkaz [příspěvku na blogu](https://blogs.technet.microsoft.com/enterprisemobility/2016/09/15/cleaning-up-the-azure-ad-and-microsoft-account-overlap/), od týmu Microsoft Identity, další informace.

### <a name="defining-an-email-address-as-a-personal-account"></a>Definování e-mailovou adresu jako osobní účet
Po předplatné je přiřazen k odběrateli, obdrží e-mail s žádostí o navštivte https://my.visualstudio.com využívat výhod své předplatné.  Při pokusu o přihlášení, přihlášení odběru Visual Studio se nezdaří s chyba oznamující, že účet nebyl rozpoznán.  Před přihlášením se do https://my.visualstudio.com prostředí, zeptejte se vaše odběratel postupujte podle následujících pokynů.  Pokud třeba, můžete to [šablony](#notifying-your-subscribers-using-personal-accounts) oznámit vaše odběratele po přiřazení předplatné.

1. Přejděte na https://my.visualstudio.coma klikněte na tlačítko **vytvořit nový účet Microsoft**.

2. Vyplňte pole:
    - Zadejte e-mailovou adresu, který obdržel Uvítacího e-mailu v Someone@example.com pole
    - Vytvořit svoje heslo
    - Vyberte nastavení propagační
    - Klikněte na tlačítko **další**

3. Proveďte kroky ověření a klikněte na tlačítko **Další**.

4. Noví uživatelé možná muset dokončete profil Visual Studio.

5. Dané předplatné a výhody by teď měly být viditelné.

### <a name="notifying-your-subscribers-using-personal-accounts"></a>Upozornění odběratelů používání osobních účtů

Ve scénáři uvedených výše vaše odběratele obdrží "Uvítací E-mail", ale kvůli aliasy se zjistit, že nebudou moct přihlásit.  Můžete použít pod text, který má upozornit vaší odběratele výše uvedené kroky a pokud je to nutné, abyste možnosti podpory.  Nahraďte WORD % příslušné informace pro každý odběratele.

---Kopie níže (Ctrl + C),

Hello % odběratele NAME %

Byly přiřazeny předplatné sady Visual Studio a byl přesměrován k přihlášení do https://my.visualstudio.com podle Uvítacího e-mailu.  I když jde o správný webu pro použití výhody, naší organizace vyžaduje, abyste si před přístupem k webu provést několik kroků navíc.  Postupujte podle následující pokyny vám pomůže vytvořit "Account Microsoft", který je vázaný na našich podnikových e-mailovou adresu.  Po dokončení těchto kroků se použije pro přístup ke výhody odběr e-mailovou adresu.
1. Navštivte https://my.visualstudio.com

2. Klikněte na tlačítko Vytvořit nový Account Microsoft na pravé straně

3. Vyplňte formulář: 
    - Použít svou firemní e-mailovou adresu do someone@example.com pole
    - Zadejte heslo
    - Vyberte vaši volbu propagační
    - Klikněte na tlačítko Další

4. Proveďte kroky ověření účtu

5. V případě potřeby dokončete profil Visual Studio

6. Teď byste měli vidět vaše výhody

Poznámka: Při návštěvě https://my.visualstudio.com v budoucnosti, můžete být vyzváni k výběru účtu, který chcete použít (např.) "Pracovní nebo školní účet" nebo "Osobní účet").  Po provedení kroků výše, musíte využít možnost "Osobní účet".

Pokud máte problémy, kontaktujte prosím tým podpory (https://www.visualstudio.com/subscriptions/support/).

V dolní části stránky vyberte následující položky:
   - Účty, odběry a podpory fakturace
   - Z problém zvolíte předplatné přihlašovací podpory
   - Vyberte příslušnou zemi
   - Vyberte požadovanou možnost odbornou pomoc

---Konec zkopírování---