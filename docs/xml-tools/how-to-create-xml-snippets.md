---
title: 'Postupy: vytvoření fragmenty kódu XML | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: d8556dd7-1382-4af7-ba80-3e873c9416be
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f98d0cccdbd530ea20c01369860c15186487a234
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-xml-snippets"></a>Postupy: vytvoření fragmenty kódu XML
XML Editor lze použít k vytvoření nové fragmenty kódu XML. Editor zahrnuje fragmentu kódu XML, s názvem "Fragment", který je fragment často používaný pro vytvoření nové fragmenty kódu XML.  
  
## <a name="to-create-a-new-xml-snippet"></a>Chcete-li vytvořit nové fragment kódu XML  
 Chcete-li vytvořit nový kód XML fragment kódu, vytvořte nový soubor XML a používat **Vložit fragment** funkce.  
  
1.  Na **soubor** nabídky, klikněte na tlačítko **nový** a pak klikněte na **soubor**.  
  
2.  Klikněte na tlačítko **souboru XML** a pak klikněte na **otevřete**.  
  
3.  Klikněte pravým tlačítkem v podokně editor a vyberte **Vložit fragment**.  
  
4.  Vyberte **fragment kódu** ze seznamu a potom stiskněte klávesu ENTER.  
  
5.  Žádné změny fragmentu nové.  
  
6.  Z **soubor** nabídky vyberte možnost **uložit XMLFile.xml**.  
  
     **Uložit soubor jako** se zobrazí dialogové okno.  
  
7.  Zadejte název pro nový fragment kódu a vyberte **fragment kódu soubory** z **uložit jako typ** okno rozevíracího seznamu.  
  
8.  Použití **uložit v** rozevíracího seznamu změnit umístění souboru do složky Dokumenty\visual 2005\Code Snippets\XML\My fragmenty XML a potom stiskněte klávesu **Uložit**.  
  
## <a name="snippet-description"></a>Popis fragmentu kódu  
 Tato část popisuje některé klíčové prvky v tomto fragmentu kódu standardní. Další informace o schématu prvky používané fragmentů kódu XML, najdete v části [fragmenty kódu – odkaz schématu](../ide/code-snippets-schema-reference.md).  
  
### <a name="snippettype-element"></a>Element SnippetType  
 Editor podporuje dva typy fragment kódu:  
  
```xml
<SnippetTypes>  
  <SnippetType>SurroundsWith</SnippetType>  
  <SnippetType>Expansion</SnippetType>  
</SnippetTypes>  
```
  
 `Expansion` Typ Určuje, zda se zobrazí fragmentu při vyvolání **Vložit fragment** příkaz. `SurroundsWith` Typ Určuje, zda se zobrazí fragmentu při vyvolání **okolí s** příkaz.  
  
### <a name="code-element"></a>Element Code  
 `Code` Element definuje textu XML, který bude vložen při vyvolání fragmentu.  
  
> [!NOTE]
>  Fragment textu XML musí být uzavřena do `<![CDATA[...]]>` části.  
  
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
  
-   $end$ je předdefinovaná proměnná. Když uživatel stiskne klávesu ENTER a dokončete úpravu pole fragment kódu, tato proměnná Určuje, kde je šipka nahoru (^) přesunuta do.  
  
 Výše `Code` element vloží následující textu XML:  
  
```xml
<test>  
  <name>name</name>  
</test>  
```
  
 Hodnota elementu název je označena jako upravitelné oblasti.  
  
### <a name="literal-element"></a>Element Literal  
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
 [Fragmenty kódu XML](../xml-tools/xml-snippets.md)   
 [Postupy: použití fragmenty kódu XML](../xml-tools/how-to-use-xml-snippets.md)   
 [Postupy: Generování fragmentu XML ze schématu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)