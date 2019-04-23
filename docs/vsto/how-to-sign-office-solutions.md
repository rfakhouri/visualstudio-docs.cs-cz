---
title: 'Postupy: Podepisování řešení pro Office'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- certificates [Office development in Visual Studio], Office solutions
- security [Office development in Visual Studio], signing Office solutions
- signing manifests [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 1fff7555c17f4fdac43de2690f8e133cc32881db
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60101227"
---
# <a name="how-to-sign-office-solutions"></a>Postupy: Podepisování řešení pro Office
  Pokud podepíšete řešení, můžete udělit důvěryhodnosti řešení pomocí certifikátu prokázat. Můžete použít stejný certifikát pro více řešení, a všechna řešení budou důvěryhodné žádné další aktualizace zásad.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

 Když ručně upravíte aplikace a manifesty nasazení s použitím Manifest Generation and Editing Tool (*mage.exe* a *mageui.exe*), musíte znovu podepsat manifesty, abyste mohli používat. Další informace najdete v tématu [jak: Znovu podepište manifesty aplikace a nasazení](../deployment/how-to-re-sign-application-and-deployment-manifests.md).

## <a name="sign-by-using-a-certificate"></a>Podepsat pomocí certifikátu
 Certifikát je soubor, který obsahuje jedinečný klíč a identita vydavatele řešení. Můžete koupit certifikáty od certifikační autority, nebo vytvořit svůj vlastní certifikát a nechat podepsat certifikační autority.

 Visual Studio podepíše řešení pro systém Office s dočasný certifikát pro povolení ladění. Dočasný certifikát byste neměli používat v nasazeném řešení jako důkaz.

### <a name="to-sign-an-office-solution-by-using-a-certificate"></a>K podepisování řešení pro Office s použitím certifikátu

1. Na **projektu** nabídky, klikněte na tlačítko _SolutionName_**vlastnosti**.

2. Klikněte na tlačítko **podepisování** kartu.

3. Vyberte **podepsat manifesty ClickOnce**.

4. Vyhledejte certifikát kliknutím **vybírat Store** nebo **vybrat ze souboru** a přejdete k certifikátu.

5. Chcete-li ověřit, jestli se používá správný certifikát, klikněte na tlačítko **další podrobnosti** zobrazíte informace o certifikátu.

## <a name="see-also"></a>Viz také:

- [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)
- [Zajistit jeho důvěryhodnost do řešení pro systém Office](../vsto/granting-trust-to-office-solutions.md)
- [Stránka Podepisování, Návrhář projektu](../ide/reference/signing-page-project-designer.md)
