---
title: 'Postupy: automaticky verze publikování ClickOnce přírůstek | Microsoft Docs'
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
- deploying applications [ClickOnce], incrementing publish version automatically
- Publish Version property, incrementing
- ClickOnce deployment, incrementing publish version automatically
- publishing, ClickOnce
ms.assetid: 686ab88a-6305-4914-a05b-fe269cc0ae1e
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 0a0cc134dbed973681ed43830435a6ce5ae0331c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>Postupy: Automatická inkrementace verze publikování ClickOnce
Při publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, změna `Publish Version` vlastnost způsobí, že aplikace má být publikován jako aktualizace. Ve výchozím nastavení, Visual Studio automaticky zvýší `Revision` počet `Publish Version` pokaždé, když publikujete aplikaci.  
  
 Tuto funkci můžete zakázat v **publikovat** stránky **Návrhář projektu**.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-disable-automatically-incrementing-the-publish-version"></a>Chcete-li zakázat automatické zvyšování verze publikování  
  
1.  S projekt vybraný v **Průzkumníku řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte **publikovat** kartě.  
  
3.  V **verze publikování** část, zrušte **zvýšit automaticky revizi při každém vydání** zaškrtávací políčko.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: verze publikování ClickOnce sady](../deployment/how-to-set-the-clickonce-publish-version.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)