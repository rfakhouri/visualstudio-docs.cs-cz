---
title: Vlastnosti tříd domény | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, domain class
ms.assetid: a3993995-19e7-4761-a972-b1de89131a1b
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 3d5ea3d5cad378a476c9080cd56143b1600b7b4d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668426"
---
# <a name="properties-of-domain-classes"></a>Vlastnosti tříd domény
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [vlastnosti tříd domény](https://docs.microsoft.com/visualstudio/modeling/properties-of-domain-classes).  
  
Doménové třídy mají vlastnosti v následující tabulce. Informace o třídách domény najdete v tématu [porozumění modelům, třídám a vztahům](../modeling/understanding-models-classes-and-relationships.md). Další informace o tom, jak pomocí těchto vlastností najdete v tématu [přizpůsobení a rozšíření jazyka specifického pro doménu](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Vlastnost|Popis|Výchozí|  
|--------------|-----------------|-------------|  
|Modifikátor přístupu|Úroveň přístupu doménové třídy (`public` nebo `internal`).|`public`|  
|Vlastní atributy|Použít k přidání atributů do třídy zdrojový kód, který je generován z této třídy domény.|\<žádné >|  
|Generuje Double odvozené|Pokud `True`, se vygeneruje základní třídu a částečné třídy (pro podporu přizpůsobení pomocí přepisů). Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Má vlastní konstruktor|Pokud `True`, poskytneme vám vlastního konstruktoru ve zdrojovém kódu. Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Modifikátor dědičnosti|Popisuje druh dědičnosti třídy zdrojový kód, který je generován z doménové třídy (`none`, `abstract` nebo `sealed`).|`none`|  
|Základní třída|Pokud je toto doménová třída odvozena, název základní třídy.|\<žádné >|  
|Název|Název třídy této domény.|Aktuální název|  
|Obor názvů|Obor názvů této doménové třídy.|Aktuální obor názvů|  
|Poznámky|Neformální poznámky, které jsou přidružené k této doménové třídě.|\<žádné >|  
|Popis|Popis, který se používá k dokumentu uživatelského rozhraní vygenerovaného návrháře.|\<žádné >|  
|Zobrazovaný název|Název, který se zobrazí ve vygenerovaném návrháři u této doménové třídě.|\<žádné >|  
|Klíčové slovo nápovědy|Nepovinné klíčové slovo, je použít k indexování nápovědy klávesy F1 pro tuto doménovou třídu.|\<žádné >|  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástrojů jazyka specifického pro doménu](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



