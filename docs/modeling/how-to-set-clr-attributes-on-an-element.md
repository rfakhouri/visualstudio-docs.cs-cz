---
title: "Postupy: nastavení atributů CLR v elementu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.EditAttributesDialog
helpviewer_keywords: Domain-Specific Language, custom attrributes
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 91f1143e593ae63d41e15beb74612f192ec736d1
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>Postupy: Nastavování atributů CLR v elementu
Vlastní atributy jsou speciální atributy, které mohou být přidány do domény prvky, tvarů, konektory a diagramů. Můžete přidat všechny atributy, které dědí z `System.Attribute` třídy.  
  
### <a name="to-add-a-custom-attribute"></a>Chcete-li přidat vlastní atribut  
  
1.  V **DSL Explorer**, vyberte požadovaný prvek, ke které chcete přidat vlastní atribut.  
  
2.  V **vlastnosti** okno, další **vlastní atributy** vlastnosti, klikněte na tlačítko Procházet (**...** ) ikona.  
  
     **Upravit atributy** otevře se dialogové okno.  
  
3.  V **název** sloupce, klikněte na tlačítko  **\<přidat atribut >** a zadejte název atributu. Stiskněte klávesu ENTER.  
  
4.  Řádek v části název atributu zobrazí závorek. Na tomto řádku zadejte typ parametru pro atribut (například `string`), a stiskněte klávesu ENTER.  
  
5.  V **vlastnost Name** sloupce, zadejte odpovídající název, například `MyString`.  
  
6.  Click **OK**.  
  
     **Vlastní atributy** vlastnost teď zobrazuje atribut v následujícím formátu:  
  
     `[`*AttributeName* `(` *ParameterName* `=` *typ*`)]`  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástroje jazyka domény](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)