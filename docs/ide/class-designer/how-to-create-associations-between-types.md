---
title: "Postupy: vytvoření přidružení mezi typy (návrhář tříd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.classdesigner.associationline
helpviewer_keywords:
- types [Visual Studio], associations
- association lines, defining (Class Designer)
- defining association lines (Class Designer)
- associations, types
- association lines
ms.assetid: adccb9c8-2f8a-4086-9fa9-f70f99fb6e00
caps.latest.revision: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: aa4c994ffadf04c3205762d0018d18ad14ffd6c5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-associations-between-types-class-designer"></a>Postupy: vytvoření přidružení mezi typy (návrhář tříd)
Asociační čáry v Návrháři tříd zobrazují vztah tříd v diagramu. Asociační čára představuje třídu, která je typem vlastnosti nebo pole jiné třídy ve vašem projektu. Asociační čáry obecně slouží ke znázornění nejdůležitějších vztahů mezi třídami v projektu.  
  
Ačkoli můžete zobrazit všechna pole a vlastnosti jako přidružení, je vhodnější jako přidružení zobrazit pouze důležité členy nebo přidružení v závislosti na tom, co chcete v diagramu zdůraznit. (Můžete zobrazit méně důležité členy jako běžné členy nebo je zcela skrýt.)  
  
> [!NOTE]
>  Návrhář tříd podporuje pouze jednosměrná přidružení.  
  
### <a name="to-define-an-association-line-in-the-class-diagram"></a>Definování asociační čáry v diagramu tříd  
  
1.  V panelu nástrojů v Návrháři tříd, vyberte **přidružení**.  
  
2.  Nakreslete čáru mezi dvěma tvary, které chcete propojit pomocí přidružení.  
  
     V první třídě se vytvoří nová vlastnost. Tato vlastnost se zobrazí jako asociační čára (nikoli jako vlastnost v prostoru ve tvaru) s výchozím názvem. Její typ je tvar, na který asociační čára ukazuje.
  
### <a name="to-change-the-name-of-an-association"></a>Změna názvu přidružení  
  
-   Na ploše diagramu klikněte na popisek asociační linky a upravte jej.  
  
 \-nebo –  
  
1.  Klikněte na tvar, který obsahuje vlastnost zobrazenou jako přidružení.  
  
     Tvar získá fokus a jeho členy se zobrazí v okně Detaily třídy a v okně Vlastnosti.  
  
2.  V okně Detaily třídy, nebo v okně Vlastnosti upravte pole názvu vlastnosti a stiskněte klávesu Enter.  
  
     Název se aktualizuje v **podrobností třídy** okně na ose přidružení, v okně vlastností a v kódu.  
  
## <a name="see-also"></a>Viz také
[Postupy: změna mezi zápisem člena a zápisem asociace](how-to-change-between-member-notation-and-association-notation.md)