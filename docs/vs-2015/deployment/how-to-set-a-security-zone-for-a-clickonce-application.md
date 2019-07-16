---
title: 'Postupy: Nastavení zóny zabezpečení pro aplikaci ClickOnce | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
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
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9af4507d7ccd604f82aae675bf87d36c0b039b26
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68171415"
---
# <a name="how-to-set-a-security-zone-for-a-clickonce-application"></a>Postupy: Nastavení zóny zabezpečení pro aplikaci ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Při nastavování oprávnění zabezpečení pro aplikaci ClickOnce přístup ke kódu, musíte spustit na základní sadu oprávnění **zabezpečení** stránku **Návrháře projektu**.  
  
 Ve většině případů můžete také **Internet** zóny, který obsahuje omezenou sadu oprávnění, nebo **místní Intranet** zóny, který obsahuje větší sadu oprávnění. Pokud vaše aplikace požaduje vlastní oprávnění, můžete provést kliknutím **vlastní** zóně zabezpečení. Další informace o nastavení vlastních oprávnění najdete v tématu [jak: Nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).  
  
### <a name="to-set-a-security-zone"></a>Do nastavení zóny zabezpečení  
  
1. S projekt vybraný v **Průzkumníka řešení**na **projektu** klikněte na nabídku **vlastnosti**.  
  
2. Klikněte na tlačítko **zabezpečení** kartu.  
  
3. Vyberte **povolit nastavení zabezpečení ClickOnce** zaškrtávací políčko.  
  
4. Vyberte **Toto je aplikace s částečnou důvěryhodností** přepínač.  
  
     Ovládací prvky **oprávnění zabezpečení ClickOnce** oddílu jsou povolené.  
  
5. V **vaše aplikace bude provedena instalace ze zóny** rozevírací seznam, vyberte zónu zabezpečení.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu ke kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)
