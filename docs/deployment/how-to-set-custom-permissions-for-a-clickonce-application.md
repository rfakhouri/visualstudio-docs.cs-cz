---
title: "Postupy: nastavení vlastních oprávnění pro aplikaci ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, permissions
- permissions, ClickOnce applications
ms.assetid: 660459ca-ef73-44a8-b323-610001f63b93
caps.latest.revision: "17"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 671f48cfac80595832f7aeee71e0e87388f947e6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-custom-permissions-for-a-clickonce-application"></a>Postupy: Nastavení vlastních oprávnění pro aplikaci ClickOnce
Můžete nasadit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, která používá výchozí oprávnění pro zóny Internet nebo místní Intranet. Případně můžete vytvořit vlastní zónu pro konkrétní oprávnění, které aplikace potřebuje. Můžete to provést úpravou oprávnění zabezpečení na **zabezpečení** stránky **Návrhář projektu**.  
  
### <a name="to-customize-a-permission"></a>Chcete-li přizpůsobit oprávnění  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **zabezpečení** kartě.  
  
3.  Vyberte **povolení nastavení zabezpečení ClickOnce** zaškrtávací políčko.  
  
4.  Vyberte **Toto je aplikace s částečnou důvěryhodností** tlačítko.  
  
     Ovládací prvky v **oprávnění zabezpečení ClickOnce** části jsou povolené.  
  
5.  Z **vaše aplikace bude nainstalována ze zóny** rozevíracího seznamu, klikněte na tlačítko **(vlastní)**.  
  
6.  Klikněte na tlačítko **upravit oprávnění XML**.  
  
     Soubor app.manifest se otevře v editoru XML.  
  
7.  Před `</applicationRequestMinimum>` elementu, přidejte kód XML pro oprávnění, která vaše aplikace vyžaduje.  
  
    > [!NOTE]
    >  Můžete použít `ToXml` metoda oprávnění nastavená pro generování kódu XML pro manifest aplikace. Například pro vygenerování XML pro <xref:System.Security.Permissions.EnvironmentPermission> sadu oprávnění, volání <xref:System.Security.Permissions.EnvironmentPermission.ToXml%2A> metoda. Další informace o struktuře oprávnění XML naleznete v tématu [NIB: postupy: Import a nastavte oprávnění pomocí souboru XML](http://msdn.microsoft.com/en-us/dea16b54-c108-408a-ac36-cdc05f746236).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)