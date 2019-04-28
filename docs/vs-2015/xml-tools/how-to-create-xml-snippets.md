---
title: 'Postupy: Vytváření fragmentů XML | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: d8556dd7-1382-4af7-ba80-3e873c9416be
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2c7eecfb6d56d4db378882f6cd45f96454a086dd
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63421726"
---
# <a name="how-to-create-xml-snippets"></a>Postupy: Vytváření fragmentů XML
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

XML Editor lze použít k vytvoření nových fragmentů kódu XML. Editor obsahuje fragmentu XML, s názvem "Fragmentu kódu", který je často používaný text fragment kódu pro vytvoření nových fragmentů kódu XML.  
  
## <a name="to-create-a-new-xml-snippet"></a>Chcete-li vytvořit nové fragment kódu XML  
 Chcete-li vytvořit nový kód XML fragmentu kódu vytvořte nový soubor XML a použít **Vložit fragment** funkce.  
  
1. Na **souboru** nabídky, klikněte na tlačítko **nový** a potom klikněte na tlačítko **souboru**.  
  
2. Klikněte na tlačítko **soubor XML** a potom klikněte na tlačítko **otevřít**.  
  
3. Podokna editoru pravým tlačítkem a vyberte **Vložit fragment**.  
  
4. Vyberte **fragment** ze seznamu a potom stiskněte klávesu ENTER.  
  
5. Proveďte změny nového fragment kódu.  
  
6. Z **souboru** nabídky vyberte možnost **uložit XMLFile.xml**.  
  
     **Uložit soubor jako** se zobrazí dialogové okno.  
  
7. Zadejte název pro nový fragment kódu a vyberte **soubory fragmentu kódu** z **uložit jako typ** okno rozevíracího seznamu.  
  
8. Použití **uložit v** rozevíracího seznamu změnit umístění souboru do složky fragmentů XML Snippets\XML\My 2005\Code My Documents\Visual Studio a potom stiskněte klávesu **Uložit**.  
  
## <a name="snippet-description"></a>Fragment kódu popis  
 Tato část popisuje některé z klíčových prvků v tomto fragmentu kódu často používaný text. Další informace o schématu elementy používané fragmenty XML, naleznete v tématu [fragmenty kódu – odkaz schématu](../ide/code-snippets-schema-reference.md).  
  
### <a name="snippettype-element"></a>Element SnippetType  
 Editor podporuje dva typy fragment kódu:  
  
```  
<SnippetTypes>  
  <SnippetType>SurroundsWith</SnippetType>  
  <SnippetType>Expansion</SnippetType>  
</SnippetTypes>  
```  
  
 `Expansion` Typ Určuje, zda fragment kódu se zobrazí při vyvolání **Vložit fragment** příkazu. `SurroundsWith` Typ Určuje, zda fragment kódu se zobrazí při vyvolání **obklopí s** příkazu.  
  
### <a name="code-element"></a>Element Code  
 `Code` Element definuje text XML, který se vloží při vyvolání fragmentu kódu.  
  
> [!NOTE]
> Fragment textu XML musí být uzavřena do `<![CDATA[...]]>` oddílu.  
  
 Tady je `Code` element, který je vytvořen pomocí standardní fragment kódu.  
  
```  
<Code Language="XML">  
  <![CDATA[<test>  
  <name>$name$</name>  
  $selected$ $end$</test>]]>  
</Code>  
```  
  
 `Code` Element obsahuje tři proměnné.  
  
- $name$ je uživatelem definované proměnné. Vytvoří `name` element, který se má upravit hodnotu, která výchozí hodnota je "name". Uživatelem definované proměnné jsou definovány pomocí `Literal` elementu.  
  
- Vybraná $$ je předdefinovaná proměnná. Představuje text, který byl vybrán v editoru XML před vyvoláním fragmentu kódu. Umístění tato proměnná Určuje, kde se zobrazí vybraný text ve fragmentu kódu obklopující výběr.  
  
- $end$ je předdefinovaná proměnná. Když uživatel stiskne klávesu ENTER k ukončení úprav pole fragmentu kódu, tato proměnná Určuje, kde znak stříšky (^) je přesunuta do.  
  
  Výše uvedené `Code` element vloží následující text XML:  
  
```  
<test>  
  <name>name</name>  
</test>  
```  
  
 Hodnota elementu, který název je označen jako upravitelnou oblastí.  
  
### <a name="literal-element"></a>Element Literal  
 `Literal` Element slouží k identifikaci Nahrazovací text, kterou lze přizpůsobit po vložení do souboru. Například řetězcové literály, číselné hodnoty a některé názvy proměnných lze deklarovat jako literály. Můžete definovat libovolný počet literály v fragment XML dozvídat a můžete se k nim z více než jednou v tomto fragmentu kódu. Následující je příklad `Literal` element, který definuje proměnnou $name$, jejíž výchozí hodnota je "name".  
  
```  
<Literal>  
  <ID>name</ID>  
  <Default>name</Default>  
</Literal  
```  
  
 Literály najdete také na funkce. XML Editor obsahuje funkci s názvem **LookupPrefix**. **LookupPrefix** funkce vyhledá daného oboru názvů identifikátoru URI z umístění v dokumentu XML, že tento fragment kódu je vyvolána z a vrátí předponu oboru názvů, která je definována pro tento obor názvů, pokud existuje, a obsahuje dvojtečkou (:) v názvu. Následující je příklad `Literal` element, který se používá **LookupPrefix** funkce.  
  
```  
<Literal Editable="false">  
   <ID>prefix</ID>  
   <Function>LookupPrefix("namespaceURI")</Function>  
</Literal>  
```  
  
 Proměnné $ $prefix pak využijete jinde v fragment XML.  
  
## <a name="see-also"></a>Viz také  
 [Fragmentů XML](../xml-tools/xml-snippets.md)   
 [Postupy: Použití fragmentů XML](../xml-tools/how-to-use-xml-snippets.md)   
 [Postupy: Generování fragmentu kódu XML ze schématu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)
