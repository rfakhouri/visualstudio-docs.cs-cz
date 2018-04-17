---
title: Výhody WhiteSource Bolt | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 01/11/2017
ms.topic: Get-Started-Article
description: Postup aktivace předplatného WhiteSource Bolt, které jsou součástí vašeho předplatného sady Visual Studio.
ms.prod: vs-subscription
ms.technology: vs-subscriptions
searchscope: VS Subscription
ms.openlocfilehash: 0c2eed9efdcca076c20a240d60b4d38cdda23019
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
#  <a name="whitesource-bolt-in-visual-studio-subscriptions"></a>WhiteSource Bolt v sadě Visual Studio předplatných

Najít a opravit chyby zabezpečení s otevřeným zdrojem a generovat komplexní sestavy inventáře a licencí všechny součástmi typu open source v buildu.  Vyberte předplatná zahrnují šest měsíců volného přístupu sady Visual Studio. 

## <a name="activation-steps"></a>Postup aktivace

1.  Pokud chcete aktivovat vaší WhiteSource Bolt výhody, přihlaste se k [ https://my.visualstudio.com/benefits ](https://my.visualstudio.com/benefits?wt.mc_id=o~msft~docs) .

2.  Najděte dlaždici WhiteSource Bolt v části nástroje a klikněte na **získat kód** odkaz v dolní části dlaždici výhody.    

    ![Výhody WhiteSource dlaždice](_img\vs-whitesource\vs-whitesource-tile.png)

2.  Obdržíte oznámení zobrazení aktivační kód.  **Zkopírujte kód do schránky**, pak klikněte na tlačítko **aktivovat**. 

    ![WhiteSource zvýhodnění kód ](_img\vs-whitesource\vs-whitesource-code.png)

3.  Na webové stránce WhiteSource, klikněte na **aktivovat** tlačítko nebo přejděte dolů k položce **aktivovat svůj účet** části stránky.  

    ![Aktivovat výhody WhiteSource](_img\vs-whitesource\vs-whitesource-activate-page-cropped.png)

4.  V **aktivovat svůj účet** části stránky, budete řídit prostřednictvím čtyři kroky:
    - [Nainstalujte](https://marketplace.visualstudio.com/items?itemName=whitesource.ws-bolt) WhiteSource Bolt rozšíření sady Microsoft Visual Studio Marketplace. Pokud nemáte oprávnění k instalaci rozšíření, navštivte [tuto stránku](https://www.visualstudio.com/docs/marketplace/get-vsts-extensions#request).

    Klikněte na tlačítko se zeleným **nainstalovat** tlačítko Pokud používáte služby VSTS, nebo **Stáhnout** tlačítko pro Team Foundation Server.  V tomto příkladu použijeme služby VSTS. 

    ![Výhody WhiteSource instalace rozšíření](_img\vs-whitesource\vs-whitesource-download-install.png)

    - Potom vyberte účet služby VSTS, kterou chcete použít a klikněte na **potvrdit**.  (Pokud jste ještě služby VSTS, přejděte [výhody](https://my.visualstudio.com/benefits) stránky a aktivovat výhody vaší služby VSTS.)

    ![WhiteSource Benefit potvrďte účtu](_img\vs-whitesource\vs-whitesource-confirm-account.png)

    - Obdržíte potvrzení, že je rozšíření nainstalované a připravené k použití.  Klikněte na tlačítko **Začínáme** návrat na stránku WhiteSource Bolt a pokračujte.  

    ![Výhody WhiteSource instalace byla dokončena](_img\vs-whitesource\vs-whitesource-install-complete.png)

5.  Otevřete řídicí panel Projekt Visual Studio Team Services (VSTS), klikněte na **sestavení a verze** nabídky a zvolte **WhiteSource Bolt**.

    ![Výhody WhiteSource přidat rozšíření](_img\vs-whitesource\vs-whitesource-installed-cropped.png)

6. Vložte aktivační kód z dlaždice benefit WhiteSource Bolt a klikněte na tlačítko **aktivovat**. Každý aktivační kódy lze použít k aktivaci jenom jeden projektu. 

    ![Aktivovat WhiteSource zvýhodnění kód](_img\vs-whitesource\vs-whitesource-activate-code-cropped.png)

7.  Aktivací je nyní dokončen a budete mít 180 dnů zbývající u předplatného. 

8.  Budete muset přidat rozšíření WhiteSource Bolt jako jeden z vaší kroků sestavení.  Video je k dispozici na [WhiteSource Bolt stránky](https://www.whitesourcesoftware.com/whitesource_bolt_visualstudio_2017/#activate) ukáže, jak.  

9. Jakmile spustíte buildu, následující komplexní sestavy a řídicí panely se budou generovat automaticky:
    - Řídicí panel chyb zabezpečení
    - Sestava chyb zabezpečení
    - Zastaralé knihovny sestav
    - Řídicí panel licence rizik a dodržování předpisů
    - Sestava inventáře

## <a name="eligibility"></a>Podmínky
| Úrovni předplatného                                                 |     Kanály                                            | Výhody                                                          | Obnovitelných?    |
|--------------------------------------------------------------------|---------------------------------------------------------|------------------------------------------------------------------|---------------|
| Visual Studio Enterprise (standardní, roční cloud)   | VL, Azure, prodejní, vybrané NFR<sup>1</sup> | 6 měsíců       |  Ano          |
| Visual Studio Professional (standardní, roční cloud) | VL, Azure, maloobchodní                                       | Není k dispozici                                                           |NÁ         |
| Visual Studio Test Professional (standardní)                         | VL, prodejní                                              | Není k dispozici                                             |  NÁ         |
| MSDN platformy (standardní)                                          | VL, prodejní                                              | Není k dispozici                                              | NÁ         |
| Visual Studio Dev Essentials | NÁ  | Není k dispozici |NÁ |
| Visual Studio Enterprise, Visual Studio Professional (měsíční cloud) | Azure                                       | Není k dispozici                                                           |NÁ|

<sup>1</sup>*zahrnuje: Microsoft Partner Network (Enterprise).    Vyloučí: Jiné není pro prodej (NFR), Visual Studio Industry Partner (VSIP), FTE, MCT softwaru a služeb Developer, BizSpark, představte si cenná Partner společnosti Microsoft (MVP), oblast ředitel (RD), MCT softwaru a služeb, Microsoft Partner sítě () Professional).*

Nejste si jistí jaké předplatné používáte?  Připojení k [ https://my.visualstudio.com/subscriptions ](https://my.visualstudio.com/subscriptions?wt.mc_id=o~msft~docs) zobrazíte všechny odběry, které jsou přiřazeny k e-mailovou adresu. Pokud nevidíte všechny odběry, můžete mít jeden nebo více přiřadit jinou e-mailovou adresu.  Musíte se přihlásit pomocí tohoto e-mailovou adresu zobrazíte těchto předplatných. 


## <a name="support-resources"></a>Podpora prostředky
-  Potřebujete pomoc s WhiteSource Bolt?  Chat s WhiteSource Bolt zástupce v za provozu https://www.whitesourcesoftware.com/vse_whitesource_bolt/ 
-  Požádejte o pomoc s prodej, odběry, účtech a cenách pro Visual Studio předplatné sady Visual Studio [odběry podporu](https://www.visualstudio.com/subscriptions/support/).
-  Máte dotaz týkající se Visual Studio IDE, Visual Studio Team Services nebo jiné produkty Visual Studio nebo službám?  Navštivte [Visual Studio – podpora](https://www.visualstudio.com/support/). 

