---
title: "Vlastnosti vztahů domény | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, domain relationships
ms.assetid: 9ccb3dc2-b80c-4585-932f-3c5f87bafbcd
caps.latest.revision: "20"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: ded95e267195f07a003b13ccc2fb2549373e811b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="properties-of-domain-relationships"></a>Vlastnosti vztahů domény
Vlastnosti v následující tabulce jsou přidruženy k relaci domény. Informace o vztahy domén najdete v tématu [Principy modely, třídy a vztahy](../modeling/understanding-models-classes-and-relationships.md). Další informace o tom, jak používat tyto vlastnosti najdete v tématu [přizpůsobení a rozšíření jazyka domény](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Vlastnost|Popis|Výchozí|  
|--------------|-----------------|-------------|  
|Modifikátor přístupu|Úroveň přístupu relace domény (`public` nebo `internal`).|`public`|  
|Vlastní atributy|Použít k přidání atributů do zdrojového kódu třídu, která se generují z relace domény.|\<žádné >|  
|Generuje dvojitou odvozené|Pokud `True`, je generována základní třídu a částečné třídy (pro podporu přizpůsobení prostřednictvím přepsání). Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Má vlastní – konstruktor|Pokud `True`, označuje, že vlastní konstruktor je poskytována ve zdrojovém kódu. Další informace najdete v tématu [přepsání a rozšíření třídy generované](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Modifikátor dědičnosti|Popisuje typ dědičnost třídy zdrojového kódu, která se generují z relace domény (`none`, `abstract` nebo `sealed`).|\<žádné >|  
|Umožňuje duplicitní položky|Pokud `True`, duplicitní propojení relace domény může vytvářet mezi stejné dva elementy.|`False`|  
|Základní relace|Pokud je odvozený relace domény, základní relace relace domény.|\<žádné >|  
|Je vložení|Pokud `True`, doméně se vnoření vztah. Pokud `False`, relace je referenční vztah.|\<obě >|  
|Název|Název relace domény.|Aktuální název|  
|Obor názvů|Obor názvů, který je přidružený relace domény.|Aktuální obor názvů|  
|Poznámky|Neformální poznámky, které jsou přidruženy relace domény.|\<žádné >|  
|Popis|Popis, který se používá k dokumentu kódu a používá se v uživatelském rozhraní vygenerovaný návrháře.|\<žádné >|  
|Zobrazovaný název|Název, který se zobrazí v Návrháři vygenerovaný pro vztah domény.|\<žádné >|  
|Nápověda – klíčové slovo|Volitelné klíčové slovo, které se používá k indexu F1 – Nápověda pro vztah domény.|\<žádné >|  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)