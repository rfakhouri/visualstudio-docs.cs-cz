---
title: "Fragmenty kódu XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 348dbf64-3f09-4fff-b47a-a7ecdf3221cc
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 9a419d738943f780ddb6077978242ac08ff91d36
ms.sourcegitcommit: 5f436413bbb1e8aa18231eb5af210e7595401aa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2018
---
# <a name="xml-snippets"></a>Fragmenty kódu XML
Editor souborů XML nabízí funkci, *fragmenty kódu XML*, který umožňuje rychleji vytvářet soubory XML. Fragmenty kódu XML můžete znovu použít vložením do souborů. Můžete také vygenerovat data XML na základě schématu schématu XML definition language (XSD).  
  
## <a name="reusable-xml-snippets"></a>Znovu použitelné XML fragmenty kódu  
 Editor souborů XML obsahuje mnoho fragmenty kódu, které se týkají některé běžné úlohy. To umožňuje snadno vytvářet soubory XML. Vytváříte-li se schéma XML, například pomocí "Komplexní typ pořadí Element" a "Jednoduchý typ elementu" fragmenty vloží následující text do souboru XML. Pak změníte `name` hodnotu tak, aby vyhovovala vašim potřebám.  
  
```xml
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
  
 Můžete vložit fragmenty kódu dvěma způsoby. **Vložit fragment** příkaz vloží fragment kódu XML na pozici kurzoru. **Příkazu Obklopit s** příkaz zabalí fragment kódu XML kolem vybraný text. Buď jsou k dispozici obě příkazy z **IntelliSense** dílčí pod **upravit** nabídky, nebo v místní nabídce editor.  
  
 Další informace najdete v tématu [postupy: použití XML fragmenty](../xml-tools/how-to-use-xml-snippets.md).  
  
## <a name="schema-generated-xml-snippets"></a>Fragmenty kódu generovaných schématu XML  
 Editor souborů XML má také možnost Generovat fragmentu kódu XML z schématu XML. Tato funkce umožňuje naplnit elementu pomocí elementů XML vygenerovat z informace o schématu pro daný element.  
  
 Další informace najdete v tématu [postupy: vygenerování XML fragment kódu z schématu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md).  
  
## <a name="create-new-xml-snippets"></a>Vytvořit nový fragmenty kódu XML  
 Kromě fragmenty kódu, které jsou součástí [!INCLUDE[msCoName](../xml-tools/includes/msconame_md.md)] Visual Studio ve výchozím nastavení můžete také vytvořit a použít vlastní fragmenty kódu XML.  
  
 Další informace najdete v tématu [postupy: vytvoření fragmenty kódu XML](../xml-tools/how-to-create-xml-snippets.md).  
  
## <a name="see-also"></a>Viz také  
 [Editor XML](../xml-tools/xml-editor.md)