---
title: 'Postupy: Nastavení vlastních oprávnění pro aplikaci ClickOnce | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce applications, permissions
- permissions, ClickOnce applications
ms.assetid: 660459ca-ef73-44a8-b323-610001f63b93
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6fa16f3587e0d70d8604aeadb33ee7807f6a22ea
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60085659"
---
# <a name="how-to-set-custom-permissions-for-a-clickonce-application"></a>Postupy: Nastavení vlastních oprávnění pro aplikaci ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete nasadit [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikaci, která používá výchozí oprávnění pro zóny Internetu a místního intranetu. Alternativně můžete vytvořit vlastní zónu pro konkrétní oprávnění, které aplikace potřebuje. Můžete to provést úpravou oprávnění zabezpečení na **zabezpečení** stránku **Návrháře projektu**.  
  
### <a name="to-customize-a-permission"></a>Přizpůsobení oprávnění  
  
1. S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2. Klikněte na tlačítko **zabezpečení** kartu.  
  
3. Vyberte **povolit nastavení zabezpečení ClickOnce** zaškrtávací políčko.  
  
4. Vyberte **Toto je aplikace s částečnou důvěryhodností** přepínač.  
  
     Ovládací prvky **oprávnění zabezpečení ClickOnce** oddílu jsou povolené.  
  
5. Z **vaše aplikace bude provedena instalace ze zóny** rozevíracího seznamu, klikněte na tlačítko **(vlastní)**.  
  
6. Klikněte na tlačítko **editovat XML soubor oprávnění**.  
  
     Soubor app.manifest se otevře v editoru XML.  
  
7. Před `</applicationRequestMinimum>` prvku, přidejte kód XML pro oprávnění, která vaše aplikace vyžaduje.  
  
    > [!NOTE]
    >  Můžete použít `ToXml` metoda oprávnění nastavená pro generování kódu XML pro manifest aplikace. Například pro generování kódu XML pro <xref:System.Security.Permissions.EnvironmentPermission> sadu oprávnění, volání <xref:System.Security.Permissions.EnvironmentPermission.ToXml%2A> metody. Další informace o struktuře oprávnění XML naleznete v tématu [NIB: Postupy: Import oprávnění nastavit pomocí souboru XML](http://msdn.microsoft.com/dea16b54-c108-408a-ac36-cdc05f746236).  
  
## <a name="see-also"></a>Viz také  
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)   
 [Zabezpečení přístupu ke kódu pro aplikace ClickOnce](../deployment/code-access-security-for-clickonce-applications.md)   
 [Zabezpečování aplikací ClickOnce](../deployment/securing-clickonce-applications.md)
