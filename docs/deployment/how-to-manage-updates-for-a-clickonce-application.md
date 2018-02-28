---
title: "Postupy: Správa aktualizací pro aplikaci ClickOnce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.Update
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, managing applications
- ClickOnce deployment, updates
- updating data, ClickOnce
- application updates
ms.assetid: a3f23f05-e7f1-4620-b23c-2d68f9643684
caps.latest.revision: 
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: f239f13a7dcefe0ce6f2bf8c12c641e97a48ce26
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manage-updates-for-a-clickonce-application"></a>Postupy: Správa aktualizací pro aplikaci ClickOnce
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]aplikace můžete vyhledat aktualizace automaticky nebo prostřednictvím kódu programu. Jako vývojář máte spoustu flexibilitu při určení, kdy a jak se provádí kontroly aktualizací, zda jsou povinné aktualizace a které aplikace by měla vyhledat aktualizace.  
  
 Můžete nakonfigurovat aplikaci vyhledat aktualizace automaticky před spuštěním aplikace nebo v nastavených intervalech po spuštění aplikace. Kromě toho můžete zadat minimální požadovaná verze; Pokud verze uživatele je nižší než požadovaná verze je tedy instalována aktualizace.  
  
 Můžete nakonfigurovat aplikaci vyhledat aktualizace prostřednictvím kódu programu založené na události třeba požadavek uživatele. Postup "Vyhledat aktualizace pomocí programu" v tomto tématu ukazuje, jak by napsat kód, který používá <xref:System.Deployment.Application.ApplicationDeployment> třídy ke kontrole aktualizací založené na události.  
  
 Můžete také nasadit aplikaci z jednoho umístění a aktualizovat ji z jiného. Najdete v části "a zadejte jiné umístění aktualizace."  
  
 Další informace najdete v tématu [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md).  
  
 Chování aktualizace je spravováno v **aktualizace aplikace** dialogové okno, k dispozici z **publikovat** stránky **Návrhář projektu.**  
  
### <a name="to-check-for-updates-before-the-application-starts"></a>Vyhledávat aktualizace, před spuštěním aplikace  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **aktualizace** tlačítko Otevřít **aktualizace aplikace** dialogové okno.  
  
4.  V **aktualizace aplikace** dialogové okno pole, ujistěte se, že **aplikace by měla vyhledat aktualizace** je zaškrtnuté políčko.  
  
5.  V **zvolte, pokud aplikace vyhledávat aktualizace** vyberte **před spuštěním aplikace**. To zajistí, že uživatelé připojení k síti vždy použít aplikaci s nejnovějšími aktualizacemi.  
  
### <a name="to-check-for-updates-in-the-background-after-the-application-starts"></a>Vyhledávat aktualizace na pozadí po spuštění aplikace  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **aktualizace** tlačítko Otevřít **aktualizace aplikace** dialogové okno.  
  
4.  V **aktualizace aplikace** dialogové okno pole, ujistěte se, že políčko **aplikace by měla vyhledat aktualizace** je vybrána.  
  
5.  V **zvolte, pokud aplikace vyhledávat aktualizace části**, vyberte **po spuštění aplikace**. Aplikace se spustí rychleji tímto způsobem, a pak ji bude kontrolovat aktualizace na pozadí a pouze upozornit uživatele, pokud je k dispozici aktualizace. Po instalaci aktualizace se projeví až po restartování aplikace.  
  
6.  V **zadejte, jak často by měla aplikace vyhledat aktualizace** vyberte buď **zkontrolujte pokaždé, když je aplikace spuštěná** (výchozí) nebo **zkontrolujte každých** a zadejte interval čísel a času.  
  
### <a name="to-specify-a-minimum-required-version-for-the-application"></a>Chcete-li určit minimální požadovaná verze pro aplikaci  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **aktualizace** tlačítko Otevřít **aktualizace aplikace** dialogové okno.  
  
4.  V **aktualizace aplikace** dialogové okno pole, ujistěte se, že **aplikace by měla vyhledat aktualizace** je zaškrtnuté políčko.  
  
5.  Vyberte **zadejte minimální požadovaná verze pro tuto aplikaci** zaškrtněte políčko a potom zadejte **hlavní**, **menší**, **sestavení**a  **Revize** čísla pro aplikaci.  
  
### <a name="to-specify-a-different-update-location"></a>Chcete-li zadat jiné umístění aktualizace  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **aktualizace** tlačítko Otevřít **aktualizace aplikace** dialogové okno.  
  
4.  V **aktualizace aplikace** dialogové okno pole, ujistěte se, že **aplikace by měla vyhledat aktualizace** je zaškrtnuté políčko.  
  
5.  V **aktualizovat umístění** pole, zadejte umístění aktualizace s plně kvalifikovanou adresu URL, pomocí formátu http://Hostname/ApplicationName nebo cestu UNC pomocí formátu \\\Server\ApplicationName, nebo klikněte na tlačítko **Procházet** tlačítko procházení pro aktualizaci umístění.  
  
### <a name="to-check-for-updates-programmatically"></a>Ke kontrole aktualizací prostřednictvím kódu programu  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  Klikněte na tlačítko **aktualizace** tlačítko Otevřít **aktualizace aplikace** dialogové okno.  
  
4.  V **aktualizace aplikace** dialogové okno pole, ujistěte se, že **aplikace by měla vyhledat aktualizace** zaškrtnutí políčka. (Můžete volitelně vybrat toto políčko, chcete-li kontrolovat aktualizace prostřednictvím kódu programu a také nechat ClickOnce aktualizace vyhledávat automaticky.)  
  
5.  V **aktualizovat umístění** pole, zadejte umístění aktualizace s plně kvalifikovanou adresu URL, pomocí formátu http://Hostname/ApplicationName nebo cestu UNC pomocí formátu \\\Server\ApplicationName, nebo klikněte na tlačítko **Procházet** tlačítko procházení pro aktualizaci umístění. Aktualizace umístění je, kde bude aplikace vyhledávat aktualizovaná verze sám sebe.  
  
6.  Vytvoření tlačítka, položku nabídky nebo jinou položku uživatelského rozhraní na formuláři, který budou uživatelé vybírat ke kontrole aktualizací. Z obslužné rutiny této položky volejte metodu pro kontrolu a instalaci aktualizací. Ukázkový kód jazyka Visual Basic a Visual C# můžete najít pro takovou metodu v [postup: vyhledejte aplikaci aktualizace programově pomocí rozhraní API nasazení ClickOnce](../deployment/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api.md).  
  
7.  Sestavení aplikace.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Deployment.Application.ApplicationDeployment>   
 [Dialogové okno aktualizace aplikace](http://msdn.microsoft.com/en-us/8eca8743-8e68-4d04-bfd5-4dc0a9b2934f)   
 [Výběr strategie aktualizace ClickOnce](../deployment/choosing-a-clickonce-update-strategy.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: publikování aplikace ClickOnce pomocí Průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [Postupy: Programová kontrola aktualizací aplikace pomocí rozhraní API nasazení ClickOnce](../deployment/how-to-check-for-application-updates-programmatically-using-the-clickonce-deployment-api.md)