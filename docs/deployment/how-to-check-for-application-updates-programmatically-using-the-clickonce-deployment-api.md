---
title: 'Postupy: Kontrola aktualizací aplikace programově pomocí rozhraní API nasazení ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, updates
- application updates
ms.assetid: 1a886310-67c8-44e5-a382-c2f0454f887d
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 2812a12541d71d29beff453c66344f85be904f5a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
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
  
-   Postupujte podle pokynů pro nasazení aplikace pomocí Mage.exe, jak je popsáno v [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md). Při volání Mage.exe pro generování manifestu nasazení, nezapomeňte použít přepínač příkazového řádku `providerUrl`a chcete zadat adresu URL, kde by měla ClickOnce vyhledat aktualizace. Pokud vaše aplikace bude z aktualizovat [ http://www.adatum.com/MyApp ](http://www.adatum.com/MyApp), například volání ke generování manifestu nasazení může vypadat například takto:  
  
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