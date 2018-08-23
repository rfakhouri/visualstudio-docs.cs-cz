---
title: 'Postupy: nastavování atributů CLR v elementu | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.EditAttributesDialog
helpviewer_keywords:
- Domain-Specific Language, custom attrributes
ms.assetid: b3db3c74-920c-4701-9544-6f75cbe8b7c9
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: afcbadd7c7b3a18c94228e7221eda32b7117a2ed
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632186"
---
# <a name="how-to-set-clr-attributes-on-an-element"></a>Postupy: Nastavování atributů CLR v elementu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [postupy: nastavení atributů CLR v elementu](https://docs.microsoft.com/visualstudio/modeling/how-to-set-clr-attributes-on-an-element).  
  
Vlastní atributy jsou speciální atributy, které lze přidat do domény prvky, tvary, konektory a diagramy. Můžete přidat všechny atributy, které dědí z `System.Attribute` třídy.  
  
### <a name="to-add-a-custom-attribute"></a>Chcete-li přidat vlastní atribut  
  
1.  V **Průzkumník DSL**, vyberte požadovaný prvek, ke kterému chcete přidat vlastní atribut.  
  
2.  V **vlastnosti** okna, další **vlastní atributy** vlastnosti, klikněte na tlačítko Procházet (**...** ) ikonu.  
  
     **Upravit atributy** zobrazí se dialogové okno.  
  
3.  V **název** sloupce, klikněte na tlačítko  **\<přidat atribut >** a zadejte název atributu. Stiskněte klávesu ENTER.  
  
4.  Řádek pod názvem atributu zobrazuje závorky. Na tomto řádku zadejte typ parametru atributu (například `string`), a potom stiskněte klávesu ENTER.  
  
5.  V **vlastnost Name** sloupce, zadejte vhodný název, například `MyString`.  
  
6.  Klikněte na tlačítko **OK**.  
  
     **Vlastní atributy** vlastnost se nyní zobrazí atribut v následujícím formátu:  
  
     `[` *AttributeName* `(` *ParameterName* `=` *typu* `)]`  
  
## <a name="see-also"></a>Viz také  
 [Glosář nástrojů jazyka specifického pro doménu](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



