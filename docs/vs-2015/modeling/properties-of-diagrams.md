---
title: Vlastnosti diagramů | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.dsltools.dsldesigner.dsldiagram
helpviewer_keywords:
- Domain-Specific Language, diagram
ms.assetid: 00bba4b8-6aa6-4027-96cb-4f4c41a77d3c
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 287e9362162c00a5292815ebacfb8047b2a0bb7b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54799943"
---
# <a name="properties-of-diagrams"></a>Vlastnosti diagramů
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Můžete nastavit vlastnosti, které určují, jak diagramy se zobrazí ve vygenerovaném návrháři. Můžete například zadat výchozí barva textu v diagramu.  
  
 Další informace najdete v tématu [jak se definuje jazyk specifický pro doménu](../modeling/how-to-define-a-domain-specific-language.md). Další informace o tom, jak pomocí těchto vlastností najdete v tématu [přizpůsobení a rozšíření jazyka specifického pro doménu](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
 V následující tabulce jsou uvedeny vlastnosti diagramů.  
  
|Vlastnost|Popis|Výchozí|  
|--------------|-----------------|-------------|  
|Barva výplně|Barva výplně diagramu.|White|  
|Barva textu|Barva textu, který se zobrazí v diagramu.|Black|  
|Modifikátor přístupu|Modifikátor přístupu třídy (veřejné nebo interní).|Public|  
|Vlastní atributy|Umožňuje přidat atributy vytvořené třídě kódu.|\<žádné >|  
|Generuje Double odvozené|Pokud `True`, se vygeneruje základní třídu a částečné třídy (pro podporu přizpůsobení pomocí přepisů). Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md).|False|  
|Má vlastní konstruktor|Pokud `True`, poskytneme vám vlastního konstruktoru ve zdrojovém kódu. Další informace najdete v tématu [přepisování a rozšiřování třídy generované v](../modeling/overriding-and-extending-the-generated-classes.md)...|False|  
|Modifikátor dědičnosti|Popisuje druh dědičnosti třídy zdrojový kód, který je generován z diagramu (`none`, `abstract` nebo `sealed`).|Žádná|  
|Základní Diagram|Základní třída tento diagram.|(žádné)|  
|Název|Název tohoto diagramu.|Aktuální název|  
|Obor názvů|Obor názvů, který je přidružený tento diagram.|Aktuální obor názvů|  
|Reprezentovaná třída|Kořenová třída domény, který představuje tento diagram.|Pokud je k dispozici aktuální kořenová třída|  
|Poznámky|Neformální poznámky, které jsou spojeny s tímto elementem.|\<žádné >|  
|Barva výplně zveřejní jako vlastnost|Pokud `True`, může uživatel nastavit barvu výplně diagramu vygenerovaného návrháře. Nastavit, klikněte pravým tlačítkem myši na obrazec diagram a klikněte na tlačítko **přidat Explosed**.|False|  
|Zpřístupní barvu textu jako vlastnost|Pokud `True`, může uživatel nastavit barvu textu diagramu ve vygenerovaném návrháři. Nastavit, klikněte pravým tlačítkem myši na obrazec diagram a klikněte na tlačítko **přidat Explosed**.|False|  
|Popis|Popis, který se používá k dokumentu vygenerovaného návrháře.|\<žádné >|  
|Zobrazovaný název|Název, který se zobrazí ve vygenerovaném návrháři u tohoto diagramu.|\<žádné >|  
|Klíčové slovo nápovědy|Klíčové slovo, je použít k indexování nápovědy klávesy F1 pro tento diagram.|\<žádné >|  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástrojů jazyka specifického pro doménu](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
