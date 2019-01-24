---
title: 'Postupy: Implementace rozhraní (návrhář tříd) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 220f3aad7e46310ec347418c25d866d03ecc2f15
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54760360"
---
# <a name="how-to-implement-an-interface-class-designer"></a>Postupy: Implementace rozhraní (návrhář tříd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V Návrháři tříd můžete implementovat rozhraní v diagramu tříd díky připojení k třídu, která poskytuje kód pro metody rozhraní. Návrhář tříd implementaci rozhraní vygeneruje a zobrazí vztah mezi rozhraní a třídy jako vztah dědičnosti. Kreslením čáru dědičnosti mezi rozhraní a třídy nebo přetažením rozhraní ze zobrazení tříd můžete implementovat rozhraní.  
  
> [!TIP]
>  Můžete vytvořit rozhraní stejným způsobem vytvoření jiných typů. Pokud rozhraní existuje, ale nezobrazí v diagramu tříd, pak nejprve zobrazí ji. Další informace najdete v tématu [jak: Vytváření typů pomocí návrháře tříd](../ide/how-to-create-types-by-using-class-designer.md) a [jak: Zobrazení existujících typů (návrhář tříd)](../ide/how-to-view-existing-types-class-designer.md).  
  
### <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>Pro implementaci rozhraní kreslením čáru dědičnosti  
  
1. V diagramu tříd zobrazte rozhraní a třídy, která implementuje rozhraní.  
  
2. Kreslení čáru dědičnosti z třídy a rozhraní.  
  
    Lupy se zobrazí jako připojené ke třídě a popisek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje provizorní kód pro všechny členy rozhraní.  
  
   Další informace najdete v tématu [jak: Vytvoření dědičnosti mezi typy (návrhář tříd)](../ide/how-to-create-inheritance-between-types-class-designer.md).  
  
### <a name="to-implement-an-interface-from-the-class-view-window"></a>Pro implementaci rozhraní z oken zobrazení tříd  
  
1.  V diagramu tříd zobrazte třídu, která chcete implementovat rozhraní.  
  
2.  Otevřete zobrazení tříd a vyhledejte rozhraní.  
  
    > [!TIP]
    >  Pokud zobrazení tříd není otevřeno, otevřete je z **zobrazení** nabídky. Další informace o zobrazení tříd naleznete v tématu [Viewing Classes and Their Members](http://msdn.microsoft.com/71e9e8f3-261a-4e0c-87bf-5ec48b8bf333).  
  
3.  Přetáhněte uzel rozhraní do třídy obrazec v diagramu.  
  
     Lupy se zobrazí jako připojené ke třídě a popisek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje provizorní kód pro všechny členy rozhraní. v tomto okamžiku je implementovaná rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Vytváření typů pomocí návrháře tříd](../ide/how-to-create-types-by-using-class-designer.md)   
 [Postupy: Zobrazení existujících typů (návrhář tříd)](../ide/how-to-view-existing-types-class-designer.md)   
 [Postupy: Vytvoření dědičnosti mezi typy (návrhář tříd)](../ide/how-to-create-inheritance-between-types-class-designer.md)   
 [Refaktoring tříd a typů (Návrhář tříd)](../ide/refactoring-classes-and-types-class-designer.md)
