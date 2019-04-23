---
title: 'Postupy: Nastavení zóny zabezpečení pro aplikaci ClickOnce | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, security settings
- code access security, ClickOnce applications
- security zones, ClickOnce applications
ms.assetid: d3dac454-518a-44d7-a76e-ccb7b9c3a150
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 31a61dd337fce614c1271f994a42ec90f3be8acb
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60054076"
---
# <a name="how-to-set-a-security-zone-for-a-clickonce-application"></a>Postupy: Nastavení zóny zabezpečení pro aplikaci ClickOnce
Při nastavování oprávnění zabezpečení pro aplikaci ClickOnce přístup ke kódu, musíte spustit na základní sadu oprávnění **zabezpečení** stránku **Návrháře projektu**.

 Ve většině případů můžete také **Internet** zóny, který obsahuje omezenou sadu oprávnění, nebo **místní Intranet** zóny, který obsahuje větší sadu oprávnění. Pokud vaše aplikace požaduje vlastní oprávnění, můžete provést kliknutím **vlastní** zóně zabezpečení. Další informace o nastavení vlastních oprávnění najdete v tématu [jak: Nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).

### <a name="to-set-a-security-zone"></a>Do nastavení zóny zabezpečení

1. S projekt vybraný v **Průzkumníka řešení**na **projektu** klikněte na nabídku **vlastnosti**.

2. Klikněte na tlačítko **zabezpečení** kartu.

3. Vyberte **povolit nastavení zabezpečení ClickOnce** zaškrtávací políčko.

4. Vyberte **Toto je aplikace s částečnou důvěryhodností** přepínač.

     Ovládací prvky **oprávnění zabezpečení ClickOnce** oddílu jsou povolené.

5. V **vaše aplikace bude provedena instalace ze zóny** rozevírací seznam, vyberte zónu zabezpečení.

## <a name="see-also"></a>Viz také:
- [Postupy: Nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)
- [Zabezpečení aplikací ClickOnce](../deployment/securing-clickonce-applications.md)
- [Zabezpečení přístupu ke kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)
