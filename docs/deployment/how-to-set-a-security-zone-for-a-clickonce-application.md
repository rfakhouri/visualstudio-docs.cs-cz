---
title: 'Postupy: nastavení zóny zabezpečení pro aplikaci ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9be6bd056473a6cdf7d4bf3bef2aedafe5ae2143
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31564545"
---
# <a name="how-to-set-a-security-zone-for-a-clickonce-application"></a>Postupy: Nastavení zóny zabezpečení pro aplikaci ClickOnce
Při nastavování oprávnění zabezpečení pro aplikaci ClickOnce přístupu kódu, je nutné začít se základní sadou oprávnění na **zabezpečení** stránky **Návrhář projektu**.  
  
 Ve většině případů můžete také **Internet** zóny, který obsahuje omezenou sadu oprávnění, nebo **místní Intranet** zóny, který obsahuje větší sadu oprávnění. Pokud vaše aplikace vyžaduje vlastní oprávnění, můžete tak učinit výběrem **vlastní** zóny zabezpečení. Další informace o nastavení vlastních oprávnění najdete v tématu [postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md).  
  
### <a name="to-set-a-security-zone"></a>K nastavení zóny zabezpečení  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídce klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **zabezpečení** kartě.  
  
3.  Vyberte **povolení nastavení zabezpečení ClickOnce** zaškrtávací políčko.  
  
4.  Vyberte **Toto je aplikace s částečnou důvěryhodností** tlačítko.  
  
     Ovládací prvky v **oprávnění zabezpečení ClickOnce** části jsou povolené.  
  
5.  V **vaše aplikace bude nainstalována ze zóny** rozevíracího seznamu, vyberte zónu zabezpečení.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)