---
title: 'Postupy: Automatická Inkrementace ClickOnce verze publikování | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: bf59ba569b7530accf4293954606923ee614d305
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629863"
---
# <a name="how-to-automatically-increment-the-clickonce-publish-version"></a>Postupy: Automatická inkrementace verze publikování ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [jak: Automatický přírůstek verze publikování ClickOnce](https://docs.microsoft.com/visualstudio/deployment/how-to-automatically-increment-the-clickonce-publish-version).  
  
Při publikování [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikace, změna `Publish Version` vlastnosti způsobí, že aplikace má být publikován jako aktualizace. Ve výchozím nastavení, Visual Studio automaticky zvýší `Revision` počet `Publish Version` pokaždé, když publikujete aplikaci.  
  
 Toto chování lze zakázat na **publikovat** stránku **Návrháře projektu**.  
  
> [!NOTE]
>  Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení nastavení pro vývoj v sadě Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-disable-automatically-incrementing-the-publish-version"></a>Chcete-li zakázat automatické zvyšování verze publikování  
  
1.  S projekt vybraný v **Průzkumníka řešení**na **projektu** nabídky, klikněte na tlačítko **vlastnosti**.  
  
2.  Klikněte na tlačítko **publikovat** kartu.  
  
3.  V **publikovat verzi** části, zrušte **automaticky zvyšovat číslo každé vydané verze** zaškrtávací políčko.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: nastavení publikování ClickOnce verze](../deployment/how-to-set-the-clickonce-publish-version.md)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [Postupy: Publikování aplikace ClickOnce pomocí průvodce publikováním](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)



