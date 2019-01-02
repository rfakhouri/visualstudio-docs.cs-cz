---
title: Použití fragmentů XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 3a27375b-81cc-48f6-a884-e1cb8c4f78f5
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 514e3efe56c18288a596d4414512064ed4dcc157
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53940729"
---
# <a name="how-to-use-xml-snippets"></a>Postupy: Použití fragmentů XML

Fragmenty XML lze vyvolat pomocí následujících dvou příkazů v místní nabídce editoru XML. **Vložit fragment** příkaz vloží fragment kódu XML na pozici kurzoru. **Obklopit fragmentem** příkaz zabalí fragment kódu XML okolo vybraného textu. Každý fragment kódu XML určil typy fragment kódu. Typy fragment určují, zda fragment kódu je k dispozici **Vložit fragment** příkazu **obklopit fragmentem** příkazu, nebo obojí.

Po přidání fragment kódu XML editor žádné upravitelné pole v tomto fragmentu kódu je zvýrazněn žlutě a se kurzor na první pole upravitelné.

## <a name="insert-snippet"></a>Vložit fragment kódu

Následující postupy popisují, jak získat přístup k **Vložit fragment** příkazu.

> [!NOTE]
> **Vložit fragment** příkaz je také k dispozici prostřednictvím klávesové zkratky (**Ctrl**+**K**, pak **Ctrl** + **X**).

### <a name="to-insert-snippets-from-the-shortcut-menu"></a>Chcete-li vložit fragmenty kódu z místní nabídky

1. Umístěte kurzor na místo, kam chcete vložit fragment kódu XML.

2. Klikněte pravým tlačítkem a vyberte **Vložit fragment**.

   Zobrazí se seznam dostupných fragmentů XML.

3. Vyberte fragment kódu ze seznamu pomocí myši nebo zadáním názvu fragmentu kódu a stisknutím klávesy **kartu** nebo **Enter**.

### <a name="to-insert-snippets-using-the-intellisense-menu"></a>Chcete-li vložit fragmenty kódu technologie IntelliSense nabídky

1. Umístěte kurzor na místo, kam chcete vložit fragment kódu XML.

2. Z **upravit** nabídky, přejděte k **IntelliSense**a pak vyberte **Vložit fragment**.

   Zobrazí se seznam dostupných fragmentů XML.

3. Vyberte fragment kódu ze seznamu pomocí myši nebo zadáním názvu fragmentu kódu a stisknutím klávesy **kartu** nebo **Enter**.

### <a name="to-insert-snippets-through-the-intellisense-complete-word-list"></a>Chcete-li vložit fragmenty kódu technologie IntelliSense seznam dokončit slovo

1. Umístěte kurzor na místo, kam chcete vložit fragment kódu XML.

2. Začněte psát fragment kódu XML, který chcete přidat do souboru. Pokud je zapnuté automatické dokončování, zobrazí se seznam dokončit slovo technologie IntelliSense. Pokud se nezobrazí, stiskněte **Ctrl**+**místo** jej aktivovat.

3. Vyberte ze seznamu úplné slovo fragment kódu XML.

4. Stisknutím klávesy **kartu**, **kartu** vyvolat fragment kódu XML.

> [!NOTE]
> Můžou nastat případy při získání vyvolání není fragment kódu XML. Například, pokud se pokusíte vložit `xs:complexType` element v rámci `xs:element` uzlu editoru není generování fragmentu XML. Když `xs:complexType` element se používá v `xs:element` uzel, tak editor neobsahuje žádná data k vložení neexistují žádné povinné atributy nebo dílčí prvky,.

### <a name="to-insert-snippets-using-the-shortcut-name"></a>Chcete-li vložit fragmenty kódu pomocí názvu odkazu

1. Umístěte kurzor na místo, kam chcete vložit fragment kódu XML.

2. Typ `<` podokna editoru.

3. Stisknutím klávesy **Esc** zavřete seznam dokončit slovo technologie IntelliSense.

4. Zadejte místní název fragmentu kódu a stiskněte klávesu **kartu** vyvolat fragment kódu XML.

## <a name="surround-with"></a>Obklopit fragmentem

Následující postupy popisují, jak získat přístup k **obklopit fragmentem** příkazu.

> [!NOTE]
> **Obklopit fragmentem** příkaz je také k dispozici prostřednictvím klávesové zkratky (**Ctrl**+**K**, pak **Ctrl** + **S**).

### <a name="to-use-surround-with-from-the-context-menu"></a>Použití příkazu Obklopit s v místní nabídce

1. Vyberte text, který se před a za v editoru XML.

2. Klikněte pravým tlačítkem a vyberte **obklopit fragmentem**.

   Zobrazí se seznam dostupných obklopí fragmentem fragmentů XML.

3. Vyberte fragment kódu ze seznamu pomocí myši nebo zadáním názvu fragmentu kódu a stisknutím klávesy **kartu** nebo **Enter**.

### <a name="to-use-surround-with-from-the-intellisense-menu"></a>Použití příkazu Obklopit s z nabídky technologie IntelliSense

1. Vyberte text, který se před a za v editoru XML.

2. Z **upravit** nabídky, přejděte k **IntelliSense**a pak vyberte **obklopit fragmentem**.

   Zobrazí se seznam dostupných obklopí fragmentem fragmentů XML.

3. Vyberte fragment kódu ze seznamu pomocí myši nebo zadáním názvu fragmentu kódu a stisknutím klávesy **kartu** nebo **Enter**.

## <a name="use-xml-snippets"></a>Použití fragmentů XML

Po zvolení fragmentu XML je automaticky vložen text fragmentu kódu na pozici kurzoru. Jsou zvýrazněny všechna upravitelné pole v tomto fragmentu kódu a je automaticky vybrána první upravitelné pole. Aktuálně vybrané pole je zabalená.

Pokud je vybraná pole, můžete zadat novou hodnotu pro pole. Stisknutím klávesy **kartu** procházení upravitelné pole fragmentu kódu; stisknutí **Shift**+**kartu** cyklicky projde v obráceném pořadí. Kliknutím na pole umístí kurzor do pole a pole poklikáte vybere. Když je zvýrazněn pole, popisek může zobrazit, popis pole nabídky.

Je možné upravovat pouze první instance daného pole. Když toto pole je zvýrazněn, jsou uvedené další instance tohoto pole. Při změně hodnoty upravovat pole, toto pole se změní všude, kde se používá v tomto fragmentu kódu.

Stisknutím klávesy **Enter** nebo **Esc** zruší úpravu polí a editoru se vrátí do normálu.

Výchozí barvy pro pole upravovat kód fragment kódu lze změnit úpravou **pole fragmentů kódů** nastavení **písma a barvy** podokně **možnosti** dialogové okno. Další informace najdete v tématu [jak: Změna písma a barev v editoru](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md).

## <a name="see-also"></a>Viz také:

- [Fragmentů XML](../xml-tools/xml-snippets.md)
- [Postupy: Generování fragmentu XML ze schématu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)
- [Postupy: Vytváření fragmentů XML](../xml-tools/how-to-create-xml-snippets.md)