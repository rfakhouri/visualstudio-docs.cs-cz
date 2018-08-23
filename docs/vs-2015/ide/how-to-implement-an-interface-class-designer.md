---
title: 'Postupy: implementace rozhraní (návrhář tříd) | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e3626d35867902f96b7f3d48d0b7528fa16fc7a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666973"
---
# <a name="how-to-implement-an-interface-class-designer"></a>Postupy: Implementace rozhraní (návrhář tříd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: implementace rozhraní (návrhář tříd)](https://docs.microsoft.com/visualstudio/ide/how-to-implement-an-interface-class-designer).  
  
V Návrháři tříd můžete implementovat rozhraní v diagramu tříd díky připojení k třídu, která poskytuje kód pro metody rozhraní. Návrhář tříd implementaci rozhraní vygeneruje a zobrazí vztah mezi rozhraní a třídy jako vztah dědičnosti. Kreslením čáru dědičnosti mezi rozhraní a třídy nebo přetažením rozhraní ze zobrazení tříd můžete implementovat rozhraní.  
  
> [!TIP]
>  Můžete vytvořit rozhraní stejným způsobem vytvoření jiných typů. Pokud rozhraní existuje, ale nezobrazí v diagramu tříd, pak nejprve zobrazí ji. Další informace najdete v tématu [postupy: vytváření typů pomocí návrháře tříd](../ide/how-to-create-types-by-using-class-designer.md) a [postupy: zobrazení existujících typů (návrhář tříd)](../ide/how-to-view-existing-types-class-designer.md).  
  
### <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>Pro implementaci rozhraní kreslením čáru dědičnosti  
  
1.  V diagramu tříd zobrazte rozhraní a třídy, která implementuje rozhraní.  
  
2.  Kreslení čáru dědičnosti z třídy a rozhraní.  
  
     Lupy se zobrazí jako připojené ke třídě a popisek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje provizorní kód pro všechny členy rozhraní.  
  
 Další informace najdete v tématu [postupy: vytvoření dědičnosti mezi typy (návrhář tříd)](../ide/how-to-create-inheritance-between-types-class-designer.md).  
  
### <a name="to-implement-an-interface-from-the-class-view-window"></a>Pro implementaci rozhraní z oken zobrazení tříd  
  
1.  V diagramu tříd zobrazte třídu, která chcete implementovat rozhraní.  
  
2.  Otevřete zobrazení tříd a vyhledejte rozhraní.  
  
    > [!TIP]
    >  Pokud zobrazení tříd není otevřeno, otevřete je z **zobrazení** nabídky. Další informace o zobrazení tříd naleznete v tématu [Viewing Classes and Their Members](http://msdn.microsoft.com/en-us/71e9e8f3-261a-4e0c-87bf-5ec48b8bf333).  
  
3.  Přetáhněte uzel rozhraní do třídy obrazec v diagramu.  
  
     Lupy se zobrazí jako připojené ke třídě a popisek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje provizorní kód pro všechny členy rozhraní. v tomto okamžiku je implementovaná rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vytváření typů pomocí návrháře tříd](../ide/how-to-create-types-by-using-class-designer.md)   
 [Postupy: zobrazení existujících typů (návrhář tříd)](../ide/how-to-view-existing-types-class-designer.md)   
 [Postupy: vytvoření dědičnosti mezi typy (návrhář tříd)](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Refaktoring tříd a typů (Návrhář tříd)](../ide/refactoring-classes-and-types-class-designer.md)



