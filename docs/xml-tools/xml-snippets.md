---
title: Fragmentů XML
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 348dbf64-3f09-4fff-b47a-a7ecdf3221cc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 66736431b295f974bda1ca855d88cd5f5f868e7d
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526152"
---
# <a name="xml-snippets"></a>Fragmentů XML

XML editor nabízí funkci *fragmentů XML*, který umožňuje rychlejší vytváření souborů XML. Můžete znovu použít fragmentů XML tak, že vloží do vašich souborů. Můžete také vygenerovat XML dat založené na jazyk (XSD) schématu definice schématu XML.

## <a name="reusable-xml-snippets"></a>Opakovaně použitelných fragmentů XML

XML editor obsahuje mnoho fragmentů kódu, které se týkají několik běžných úloh. To umožňuje snadno vytvářet soubory XML. Pokud bylo vytváření schématu XML, například pomocí fragmenty kódu "Komplexních prvků typu sekvenci" a "Jednoduchý typ elementu" vloží následující text do souboru XML. Pak změníte `name` hodnotu tak, aby odpovídala vašim potřebám.

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

Fragmenty kódu můžete vložit dvěma způsoby. **Vložit fragment** příkaz vloží fragment kódu XML na pozici kurzoru. **Obklopit fragmentem** příkaz zabalí fragment kódu XML okolo vybraného textu. Buď nejsou k dispozici i příkazy z **IntelliSense** podnabídky **upravit** nabídky, nebo v místní nabídce editoru.

Další informace najdete v tématu [jak: Použití fragmentů XML](../xml-tools/how-to-use-xml-snippets.md).

## <a name="schema-generated-xml-snippets"></a>Generované schéma fragmentů XML

XML editor má také možnost generování fragmentu XML ze schématu XML. Tato funkce umožňuje naplnit k elementu pomocí elementů XML generované informace o schématu pro daný element. Další informace najdete v tématu [jak: Generování fragmentu XML ze schématu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md).

## <a name="create-new-xml-snippets"></a>Vytvoření nových fragmentů kódu XML

Kromě fragmenty kódu, které jsou součástí sady Visual Studio ve výchozím nastavení můžete také vytvořit a použití vlastních fragmentů XML. Další informace najdete v tématu [jak: Vytváření fragmentů XML](../xml-tools/how-to-create-xml-snippets.md).

## <a name="see-also"></a>Viz také:

- [Fragmenty kódu v sadě Visual Studio](../ide/code-snippets.md)
- [XML editor](../xml-tools/xml-editor.md)