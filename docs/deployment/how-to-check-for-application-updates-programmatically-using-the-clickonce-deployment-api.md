---
title: "Postupy: Kontrola aktualizací aplikace programově pomocí rozhraní API nasazení ClickOnce | Microsoft Docs"
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
- ClickOnce deployment, updates
- application updates
ms.assetid: 1a886310-67c8-44e5-a382-c2f0454f887d
caps.latest.revision: "9"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 02e6a4c0b69bf9e9d6170175b4324ccb226854e2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api"></a>Postupy: Programová kontrola aktualizací aplikace pomocí rozhraní API nasazení ClickOnce
ClickOnce nabízí dva způsoby, jak se aktualizace aplikace po nasazení. V metodě první můžete nakonfigurovat nasazení ClickOnce automaticky vyhledávat aktualizace v určitých intervalech. V druhé metody můžete napsat kód, který používá <xref:System.Deployment.Application.ApplicationDeployment> třídy ke kontrole aktualizací založené na události, jako je například požadavek uživatele.  
  
 Následující postupy ukazují některé kódy pro provádění programových aktualizací a také popisují, jak nakonfigurovat nasazení ClickOnce, chcete-li povolit kontroly programových aktualizací.  
  
 Aby bylo možné aktualizovat aplikaci ClickOnce prostřednictvím kódu programu, musíte zadat umístění pro aktualizace. To se někdy označuje jako zprostředkovatel nasazení. Další informace o nastavení této vlastnosti najdete v tématu [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
> [!NOTE]
>  Můžete také použít technik popsaných níže nasazení aplikace z jednoho umístění, ale aktualizace z jiného. Další informace najdete v tématu [postupy: určení alternativního umístění pro nasazení aktualizace](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md).  
  
### <a name="to-check-for-updates-programmatically"></a>Ke kontrole aktualizací prostřednictvím kódu programu  
  
1.  Vytvořte novou aplikaci Windows Forms pomocí upřednostňované nástrojů příkazového řádku nebo visual.  
  
2.  Vytvořte jakékoli tlačítko, položku nabídky nebo jinou položku uživatelského rozhraní mají uživatelé vyberte ke kontrole aktualizací. Z obslužné rutiny této položky volejte metodu kontrolovat a instalovat aktualizace.  
  
     [!code-csharp[ClickOnceAPI#6](../deployment/codesnippet/CSharp/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.cs)]
     [!code-cpp[ClickOnceAPI#6](../deployment/codesnippet/CPP/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.cpp)]
     [!code-vb[ClickOnceAPI#6](../deployment/codesnippet/VisualBasic/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api_1.vb)]  
  
3.  Kompilace aplikace.  
  
### <a name="using-mageexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Použití Mage.exe k nasazení aplikace, která kontroluje aktualizace prostřednictvím kódu programu  
  
-   Postupujte podle pokynů pro nasazení aplikace pomocí Mage.exe, jak je popsáno v [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Při volání Mage.exe pro generování manifestu nasazení, nezapomeňte použít přepínač příkazového řádku `providerUrl`a chcete zadat adresu URL, kde by měla ClickOnce vyhledat aktualizace. Pokud vaše aplikace bude z aktualizovat [http://www.adatum.com/MyApp](http://www.adatum.com/MyApp), například volání ke generování manifestu nasazení může vypadat například takto:  
  
    ```  
    mage -New Deployment -ToFile WindowsFormsApp1.application -Name "My App 1.0" -Version 1.0.0.0 -AppManifest 1.0.0.0\MyApp.manifest -providerUrl http://www.adatum.com/MyApp/MyApp.application  
    ```  
  
### <a name="using-mageuiexe-to-deploy-an-application-that-checks-for-updates-programmatically"></a>Pomocí MageUI.exe k nasazení aplikace, která kontroluje aktualizace prostřednictvím kódu programu  
  
-   Postupujte podle pokynů pro nasazení aplikace pomocí Mage.exe, jak je popsáno v [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Na **možnosti nasazení** nastavte **umístění spuštění** pole do manifestu aplikace ClickOnce vyhledávat aktualizace. Na **možnosti aktualizace** zrušte **této aplikace by měla vyhledat aktualizace** zaškrtávací políčko.  
  
## <a name="net-framework-security"></a>Zabezpečení rozhraní .NET Framework  
 Aplikace musí mít plná oprávnění pro použití programových aktualizací.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: určení alternativního umístění pro aktualizace nasazení](../deployment/how-to-specify-an-alternate-location-for-deployment-updates.md)   
 [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)