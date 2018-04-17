---
title: Přiřazení licencí odběry Visual Studio | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
description: Zjistěte, jak mohou správci přiřadit licence odběratele
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 62336656e551a085c6c8753e6baea06730f49510
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="assigning-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>Přiřazování licencí na portálu správce předplatných Visual Studio

Jako správce předplatného sady Visual Studio můžete portál správce Visual Studio odběry přiřadit odběry pro jednotlivé uživatele.  
Můžete přiřadit jednu po druhé, nebo použít funkci "hromadné přidání" k nahrání seznam odběratelé s jejich informace o předplatném snadno a rychle. 

## <a name="assigning-a-single-user"></a>Přiřazení jenom jednoho konkrétního uživatele
Pokud máte k dispozici licence pro předplatné sady Visual Studio, můžete přiřadit těchto licencí pro nové uživatele pro ně pro přístup k jejich odběru výhody. 
1.  Přihlaste se k [portálu správce](https://manage.visualstudio.com)

2.  Přiřadit jeden odběratel Visual Studio, v horní části tabulky, klikněte na tlačítko **přidat**.

    ![Přidat odběratele](_img\assign-license-add\assign-license-add.png)

3.  Zadejte informace do polí formuláře pro nové odběratele. Pokud vaše organizace používá Azure Active Directory, v tomto poli funguje jako funkce vyhledávání, která se v aktuálním adresáři najít účastníka, takže můžete vybrat správné uživatelské ve výsledcích hledání. Jakmile vyberete osoba, jeho název, přihlášení e-mailu a e-mailové oznámení bude automaticky vyplnit jak vidíte níže. 

    Pokud má vaše organizace jiný e-mail pro příjem e-mailů než ten, který se má použít pro přihlášení, máte možnost pro zadání ho sem. Vyberte na odkaz, který označuje "Jinou e-mailovou komunikaci než přihlášení?". 

    **Přístup ke stažení:**  
    Pokud chcete mít přístupu pro stahování softwaru při zápisu do tohoto odběratele [Visual Studio odběry portál](https://my.visualstudio.com?wt.mc_id=o~msft~docs), ponechte zaškrtnutým políčkem stahování. Pokud zvolíte možnost zrušte zaškrtnutí tohoto políčka, uživatel nebude mít přístup k stažení softwaru, ale bude mít dál přístup k všechny další výhody, které jsou zahrnuty v rámci předplatného. 
    
    Po dokončení výběru možnosti tohoto odběratele, klikněte na tlačítko **přidat**.

    ![Zadejte informace o odběru](_img\assign-license-add\add-subscriber-1.png)
    ![zadejte informace o odběru](_img\assign-license-add\add-subscriber-2.png)

4.  Po přidání odběratele, se automaticky odesílat e-mailu přiřazení nové odběratele s další pokyny. Přiřazení e-mailu můžete kdykoli znovu odeslat výběrem odběratele a kliknutím na **znovu odeslal** tlačítka v horní nabídce.

    ![Přidat odběratele](_img\assign-license-add\add-subscriber-complete.png)

## <a name="bulk-assignments"></a>Hromadné přiřazení
1.  Chcete-li přidat více odběrateli, přejděte na **Odběratelé, kteří** kartě. Na pásu karet v horní části, klikněte na tlačítko **hromadné přidání**. 

    ![Hromadné přidání](_img\assign-license-add\bulk-assign-add.png)

2. Hromadně přiřadit používá šablonu aplikace Microsoft Excel nahrát odběratele. V dialogovém okně nahrát více odběrateli, klikněte na tlačítko **Stáhnout** stáhnout šablonu. Vždy stáhněte nejnovější verzi této šablony. Pokud používáte starší verzi, odeslání hromadné se pravděpodobně nezdaří.

    ![Nahrát několik odběratele](_img\assign-license-add\bulk-assign-upload.png)

3.  Vyplňte pole pomocí informací pro jednotlivce, které chcete přiřadit odběry v tabulce aplikace Excel. Odkaz je volitelné pole. Pokud jste vyplnili všechny součástí šablony nesprávně, měli byste vidět chybová zpráva s popisem problému. Uložte soubor na vašem pevném disku po dokončení.
**K zajištění načtení smooth, sledujte následující osvědčené postupy:**
    - Ujistěte se, že žádná z pole formuláře obsahovat čárky.
    - Odebrání mezer před a po polí formuláře, jako jsou jména uživatelů.
    - Zajistěte, aby se jména uživatelů neobsahují mezery mezi názvy první nebo poslední dvě části (například dvě části křestní jméno, například "Maggie může" by neměl být zadán jako "Maggie může" jako systém nebude trim volné místo) ![hromadné přidání šablony](_img\assign-license-add\bulk-template.png)

4.  Vrátit na portál pro správu předplatných Visual Studio a v dialogovém okně nahrát více odběrateli, klikněte na tlačítko **Procházet**. Přejděte k souboru aplikace Excel, který jste uložili a klikněte na tlačítko **OK**. Průběh nahrávání se zobrazí na obrazovce. 

    ![Hromadné přidání nahrávání](_img\assign-license-add\bulk-assign-upload-2.png)

Pokud šablona obsahuje chyby, nahrávání se nezdaří a se zobrazí chyby tak můžete opravte šablony a opakujte pokus hromadné nahrávání.

   ![Nahrát služeb při selhání](_img\assign-license-add\bulk-assign-upload-fail.png)

Až se nahrávání úspěšná, zobrazí se seznam odběratele a potvrzovací zpráva.

   ![Nahrát dokončení](_img\assign-license-add\bulk-assign-upload-complete.png)