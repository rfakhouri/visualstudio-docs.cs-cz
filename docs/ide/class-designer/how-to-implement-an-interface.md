---
title: "Postupy: implementace rozhraní (návrhář tříd) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interfaces [Visual Studio], implementing
- interfaces [Visual Studio]
ms.assetid: 81d2cf46-7f60-448c-83e3-1d16bb88ca36
caps.latest.revision: "16"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 469e7876900c61589afac089b848bd712703b1e6
ms.sourcegitcommit: 64c7682ec3a2cbea684e716803398d4278b591d1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/15/2017
---
# <a name="how-to-implement-an-interface-class-designer"></a>Postupy: Implementace rozhraní (návrhář tříd)
V Návrháři tříd je možné implementovat rozhraní v diagramu tříd propojením na třídu, která obsahuje kód pro metody rozhraní. Návrhář tříd generuje implementace rozhraní a zobrazí vztah mezi rozhraní a třídy jako vztah dědičnosti. Kreslení řádku s dědičnosti mezi rozhraní a třídy nebo přetažením rozhraní ze zobrazení tříd můžete implementovat rozhraní.  
  
> [!TIP]
>  Můžete vytvořit rozhraní stejným způsobem jako vytvoříte jiné typy. Pokud jste rozhraní existuje, ale nezobrazí v diagramu tříd, pak nejdřív zobrazte. Další informace najdete v tématu [postupy: vytváření typů pomocí návrháře tříd](how-to-create-types.md) a [postupy: zobrazení existujících typů](how-to-view-existing-types.md).  
  
### <a name="to-implement-an-interface-by-drawing-an-inheritance-line"></a>K implementaci rozhraní podle kreslení řádku s dědičnosti  
  
1.  Na diagramu tříd zobrazení rozhraní a třídy, která implementuje rozhraní.  
  
2.  Zakreslit řádku s dědění ze třídy a rozhraní.  
  
     Typu Lupa se zobrazí připojené k třídě a štítek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje zástupných procedur pro všechny členy rozhraní.  
  
 Další informace najdete v tématu [postupy: vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md).  
  
### <a name="to-implement-an-interface-from-the-class-view-window"></a>K implementaci rozhraní z okna zobrazení tříd  
  
1.  V diagramu tříd zobrazení třídu, která chcete implementovat rozhraní.  
  
2.  Otevřete zobrazení tříd a vyhledejte rozhraní.  
  
    > [!TIP]
    >  Pokud zobrazení tříd není otevřený, otevřete zobrazení tříd z **zobrazení** nabídky. Další informace o zobrazení tříd najdete v tématu [zobrazení třídy a jejich členové](http://msdn.microsoft.com/en-us/71e9e8f3-261a-4e0c-87bf-5ec48b8bf333).  
  
3.  Přetáhněte uzel rozhraní tvar – třída v diagramu.  
  
     Typu Lupa se zobrazí připojené k třídě a štítek s názvem rozhraní identifikuje vztah dědičnosti. Visual Studio generuje zástupných procedur pro všechny členy rozhraní; v tomto okamžiku se implementuje rozhraní.  
  
## <a name="see-also"></a>Viz také
[Postupy: vytváření typů pomocí návrháře tříd](how-to-create-types.md)   
[Postupy: zobrazení existujících typů](how-to-view-existing-types.md)   
[Postupy: vytvoření dědičnosti mezi typy](how-to-create-inheritance-between-types.md)   
[Refaktoring tříd a typů](refactoring-classes-and-types.md)