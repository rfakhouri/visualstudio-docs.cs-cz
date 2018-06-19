---
title: 'Postupy: vytvoření fragmenty kódu XML'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d8556dd7-1382-4af7-ba80-3e873c9416be
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ae09c578eac5a4acbfa9c169ba175fe557872da5
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/25/2018
ms.locfileid: "34548541"
---
# <a name="how-to-create-xml-snippets"></a>Postupy: vytvoření fragmenty kódu XML

XML Editor lze použít k vytvoření nové fragmenty kódu XML. Editor zahrnuje fragmentu kódu XML, s názvem "Fragment", který je fragment často používaný pro vytvoření nové fragmenty kódu XML.

## <a name="to-create-a-new-xml-snippet"></a>Chcete-li vytvořit nové fragment kódu XML

 Chcete-li vytvořit nový kód XML fragment kódu, vytvořte nový soubor XML a používat **Vložit fragment** funkce.

1.  Na **soubor** nabídky, klikněte na tlačítko **nový** a pak klikněte na **soubor**.

2.  Klikněte na tlačítko **souboru XML** a pak klikněte na **otevřete**.

3.  Klikněte pravým tlačítkem v podokně editor a vyberte **Vložit fragment**.

4.  Vyberte **fragment kódu** ze seznamu a stiskněte klávesu **Enter**.

5.  Žádné změny fragmentu nové.

6.  Z **soubor** nabídky vyberte možnost **uložit XMLFile.xml**.

     **Uložit soubor jako** se zobrazí dialogové okno.

7.  Zadejte název pro nový fragment kódu a vyberte **fragment kódu soubory** z **uložit jako typ** okno rozevíracího seznamu.

8.  Použití **uložit v** rozevíracího seznamu můžete změnit umístění souboru *Dokumenty\visual 2005\Code Snippets\XML\My XML fragmenty* složku a potom stiskněte klávesu **Uložit**.

## <a name="snippet-description"></a>Popis fragmentu kódu

 Tato část popisuje některé klíčové prvky v tomto fragmentu kódu standardní. Další informace o schématu prvky používané fragmentů kódu XML, najdete v části [referenční dokumentace schématu fragmenty kódu](../ide/code-snippets-schema-reference.md).

### <a name="snippettype-element"></a>SnippetType element

 Editor podporuje dva typy fragment kódu:

```xml
<SnippetTypes>
  <SnippetType>SurroundsWith</SnippetType>
  <SnippetType>Expansion</SnippetType>
</SnippetTypes>
```

 `Expansion` Typ Určuje, zda se zobrazí fragmentu při vyvolání **Vložit fragment** příkaz. `SurroundsWith` Typ Určuje, zda se zobrazí fragmentu při vyvolání **okolí s** příkaz.

### <a name="code-element"></a>Element kódu

 `Code` Element definuje textu XML, který bude vložen při vyvolání fragmentu.

> [!NOTE]
> Fragment textu XML musí být uzavřena do `<![CDATA[...]]>` části.


 Tady je `Code` element, který je vytvořen pomocí fragmentu standardní.

```xml
<Code Language="XML">
  <![CDATA[<test>
  <name>$name$</name>
  $selected$ $end$</test>]]>
</Code>
```

 `Code` Element zahrnuje tři proměnné.

-   $name$ je uživatelem definované proměnné. Vytvoří `name` element, který má upravovat hodnotu, která bude jako výchozí nastavena na "name". Uživatelem definované proměnné jsou definovány pomocí `Literal` elementu.

-   vybrané $$ je předdefinovaná proměnná. Reprezentuje text, který byl vybrán v editoru XML před vyvoláním fragmentu. Umístění tato proměnná Určuje, kde se zobrazí vybraný text ve fragmentu kódu, která obklopuje výběr.

-   $end$ je předdefinovaná proměnná. Když uživatel stiskne **Enter** dokončíte úpravy polí fragment kódu, tato proměnná Určuje, kde je šipka nahoru (^) přesunuta do.

 Výše `Code` element vloží následující textu XML:

```xml
<test>
  <name>name</name>
</test>
```

 Hodnota elementu název je označena jako upravitelné oblasti.

### <a name="literal-element"></a>Literál elementu

 `Literal` Element se používá k identifikaci Nahrazovací text, kterou lze přizpůsobit po vložení do souboru. Například literály, číselných hodnot a některé názvy proměnných lze deklarovat jako literály. Můžete definovat libovolný počet literály fragment XML a mohou odkazovat na je více než jednou. ze v tomto fragmentu kódu. Tady je příklad `Literal` element, který definuje proměnnou $name$, jejíž výchozí hodnota je "name".

```xml
<Literal>
  <ID>name</ID>
  <Default>name</Default>
</Literal
```

 Literály můžete se také podívat na funkce. Editor souborů XML obsahuje funkci s názvem **LookupPrefix**. **LookupPrefix** funkce vyhledává daný identifikátor URI oboru názvů z umístění v dokumentu XML tento fragment kódu je volána z a vrátí předponu oboru názvů, který je definovaný pro tento obor názvů, pokud existuje, a obsahuje dvojtečku (:) Tento název. Tady je příklad `Literal` element, který používá **LookupPrefix** funkce.

```xml
<Literal Editable="false">
   <ID>prefix</ID>
   <Function>LookupPrefix("namespaceURI")</Function>
</Literal>
```

 Proměnná $ $prefix se pak použít jinde v vaší fragment kódu XML.

## <a name="see-also"></a>Viz také

- [Fragmenty kódu XML](../xml-tools/xml-snippets.md)
- [Postupy: použití XML fragmenty kódu](../xml-tools/how-to-use-xml-snippets.md)
- [Postupy: generování fragmentu kódu XML z schématu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)