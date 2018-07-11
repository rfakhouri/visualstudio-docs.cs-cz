---
title: Přiřazení licencí pro předplatná sady Visual Studio | Dokumentace Microsoftu
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 10/03/2017
ms.topic: Get-Started-Article
description: Zjistěte, jak správci mohou přiřadit licence pro předplatitele
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: d0dbd509d60ed3528186e41c98f374ab6db60fa3
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2018
ms.locfileid: "36327021"
---
# <a name="assigning-licenses-in-the-visual-studio-subscriptions-administrator-portal"></a>Přiřazení licencí na portálu správce předplatných sady Visual Studio

Jako správce předplatných sady Visual Studio můžete použít správce portálu předplatných sady Visual Studio k přiřazení předplatných pro jednotlivé uživatele.  
Můžete přiřazovat postupně po jednom, nebo použít funkci "hromadné přidání" nahrát seznam předplatitelů s informacemi o předplatné snadno a rychle. 

## <a name="assigning-a-single-user"></a>Přiřazení jednoho uživatele.
Pokud máte k dispozici licence pro předplatná sady Visual Studio, můžete tyto licence přiřadit k novým uživatelům pro ně přístup svých předplatitelských výhod. 
1.  Přihlaste se k [portálu správce](https://manage.visualstudio.com)

2.  Přiřadit jednoho předplatitele sady Visual Studio, v horní části v tabulce, klikněte na tlačítko **přidat**.
   
3.  Zadejte informace do polí formuláře pro nové předplatitele. Pokud vaše organizace používá Azure Active Directory, toto pole funguje jako vyhledávací funkce, která se najít v aktuálním adresáři, můžete vybrat správný uživatel ve výsledcích hledání. Jakmile vyberete osoby, své jméno, přihlašovací e-mailu a oznámení e-mailu se automaticky vyplní jak vidíte níže. 

    Pokud vaše organizace nepoužívá Azure Active Directory (Azure AD), ale má jinou e-mailu pro příjem e-mailů než ten, který se má použít pro přihlášení, máte možnost zadat ho tady. Vyberte hypertextový odkaz s názvem "Přidat jiný e-mail pro přijímání komunikace". 

    **Přístup k souborům ke stažení:**  
    Pokud chcete, aby přístupu k souborům ke stažení softwaru při přihlašování do tohoto předplatného [portál předplatného sady Visual Studio](https://my.visualstudio.com?wt.mc_id=o~msft~docs), ujistěte se, že nechat tento přepínač stahování povoleno. Pokud budete chtít zakázat soubory ke stažení, uživatel nebude mít přístup k souborům ke stažení softwaru, ale budou mít dál přístup ke všem výhodám zahrnutý v předplatném. 
    
    Až dokončíte výběrem možnosti tohoto odběratele, klikněte na tlačítko **přidat**.

    <img alt="Enter subscriber information" src="_img\assign-license-add\add-subscriber-1.png" style="border: 1px solid #CCCCCC" />
    <img alt="Enter subscriber information" src="_img\assign-license-add\add-subscriber-2.png" style="border: 1px solid #CCCCCC" />

4.  Po přidání odběratele, E-mail s přiřazením automaticky se pošle na nový odběratel se další pokyny. Můžete kdykoli znovu odeslat E-mail s přiřazením tak odběratele vyberete a kliknete na **znovu odeslal** tlačítko v horní nabídce.


## <a name="bulk-assignments"></a>Hromadné přiřazení
1.  Chcete-li přidat současně několik předplatitelů, přejděte na **spravovat předplatitele** kartu. Na pásu karet v horní části klikněte na tlačítko **hromadné přidání**. 

2. Hromadné přiřazení používá šablonu aplikace Microsoft Excel k odeslání odběratele. V dialogovém okně nahrát několik předplatitelů klikněte na tlačítko **Stáhnout** stáhnout šablonu. Kdykoli stáhněte nejnovější verzi této šablony. Pokud používáte starší verzi, hromadné načtení může selhat.

3.  V Excelovém listu vyplňte pole s informacemi pro jednotlivce, který chcete přiřadit odběrů. Odkaz je volitelné pole. Pokud jste vyplnili všechny části šablony nesprávně, zobrazí chybová zpráva s popisem problému. Uložte soubor místně až to bude hotové.
**Zajistit hladký průběh nahrávání, dodržujte následující osvědčené postupy:**
    - Ujistěte se, že žádná z polí formuláře obsahovat čárky.
    - Odeberte mezery před a po polí formuláře, jako jsou jména uživatelů.
    - Jména uživatelů nesmí obsahovat mezery mezi dvěma částmi první nebo poslední názvy (třeba dvě části křestní jméno jako je například "Maggie může" by neměl být typu "Maggie může" jako systém nebude trim místo navíc.)

4.  Vrátit k portálu pro správu předplatných sady Visual Studio a v dialogovém okně nahrát několik předplatitelů, klikněte na tlačítko **Procházet**. Přejděte do Excelového souboru, který jste uložili a klikněte na tlačítko **OK**. Průběh nahrávání se zobrazí na obrazovce. 

    <img alt="Bulk add upload" src="_img\assign-license-add\bulk-assign-upload-2.png" style="border: 1px solid #CCCCCC" />

Pokud šablona obsahuje chyby, nahrávání se nezdaří a zobrazí se chyby tak můžete opravit šablony a pokuste se znovu hromadné načtení.
    <img alt="Upload fail" src="_img\assign-license-add\bulk-assign-upload-fail.png" style="border: 1px solid #CCCCCC" />

Při nahrání je úspěšné, zobrazí se vám seznam předplatitelů a potvrzovací zpráva.

