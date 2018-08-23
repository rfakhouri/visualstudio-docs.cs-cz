---
title: Fragmenty XML | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 348dbf64-3f09-4fff-b47a-a7ecdf3221cc
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bae360d1aea43006138397b3bed2857a2b1dad59
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676924"
---
# <a name="xml-snippets"></a>Fragmenty XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [fragmentů XML](https://docs.microsoft.com/visualstudio/xml-tools/xml-snippets).  
  
  
XML Editor nabízí funkci *fragmentů XML*, který umožňuje rychlejší vytváření souborů XML. Můžete znovu použít fragmentů XML tak, že vloží do vašich souborů. Můžete také vygenerovat data XML na základě schématu schématu XML definice jazyk (XSD).  
  
## <a name="reusable-xml-snippets"></a>Opakovaně použitelné XML fragmentů  
 XML Editor obsahuje mnoho fragmentů kódu, které se týkají několik běžných úloh. To umožňuje snadno vytvářet soubory XML. Pokud bylo vytváření schématu XML, například pomocí "Komplexních prvků typu sekvenci" a "Jednoduchý typ elementu" fragmenty kódu vloží následující text do souboru XML. Pak změníte `name` hodnotu tak, aby odpovídala vašim potřebám.  
  
```  
<xs:element name="name">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="name">  
        <xs:simpleType>  
          <xs:restriction base="xs:string"></xs:restriction>  
        </xs:simpleType>  
      </xs:element>  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Fragmenty kódu můžete vložit dvěma způsoby. **Vložit fragment** příkaz vloží fragment kódu XML na pozici kurzoru. **Obklopit fragmentem** příkaz zabalí fragment kódu XML okolo vybraného textu. Buď nejsou k dispozici i příkazy z **IntelliSense** podnabídky **upravit** nabídky, nebo v místní nabídce editoru.  
  
 Další informace najdete v tématu [postupy: použití fragmentů XML](../xml-tools/how-to-use-xml-snippets.md).  
  
## <a name="schema-generated-xml-snippets"></a>Generované schématu XML fragmentů  
 XML editor má také možnost generování fragmentu XML ze schématu XML. Tato funkce umožňuje naplnit k elementu pomocí elementů XML generované informace o schématu pro daný element.  
  
 Další informace najdete v tématu [postupy: generování fragmentu kódu z jazyka XML schématu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md).  
  
## <a name="create-new-xml-snippets"></a>Vytvoření nových fragmentů kódu XML  
 Kromě fragmenty kódu, které jsou součástí [!INCLUDE[msCoName](../includes/msconame-md.md)] Visual Studio ve výchozím nastavení můžete také vytvořit a použít vlastní fragmenty kódu XML.  
  
 Další informace najdete v tématu [postupy: vytváření fragmentů XML](../xml-tools/how-to-create-xml-snippets.md).  
  
## <a name="see-also"></a>Viz také  
 [Editor XML](../xml-tools/xml-editor.md)



