---
title: "Postupy: použití fragmenty XML | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a27375b-81cc-48f6-a884-e1cb8c4f78f5
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: d442dbf376d5615b6c10842c16d01183fc70056a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-xml-snippets"></a>Postupy: použití fragmenty kódu XML
Pomocí následujících příkazů v místní nabídce editoru XML můžete vyvolat fragmenty kódu XML. **Vložit fragment** příkaz vloží fragment kódu XML na pozici kurzoru. **Příkazu Obklopit s** příkaz zabalí fragment kódu XML kolem vybraný text. Každý fragment kódu XML určil typy fragment kódu. Typy fragment kódu určit, zda je k dispozici v tomto fragmentu kódu **Vložit fragment** příkaz, **příkazu Obklopit s** příkaz nebo obojí.  
  
 Po tomto fragmentu kódu XML se přidal do editoru, všechna upravitelné pole v tomto fragmentu kódu jsou vyznačené na žlutý a kurzor je nastavený na první upravitelné pole.  
  
## <a name="insert-snippet"></a>Vložit fragment kódu  
 Následující postupy popisují, jak získat přístup **Vložit fragment** příkaz.  
  
> [!NOTE]
>  **Vložit fragment** příkaz je také k dispozici prostřednictvím klávesové zkratky (CTRL + K, pak CTRL + X).  
  
#### <a name="to-insert-snippets-from-the-shortcut-menu"></a>Chcete-li vložit fragmenty kódu z místní nabídky  
  
1.  Umístěte kurzor na místo, kam chcete vložit fragment kódu XML.  
  
2.  Klikněte pravým tlačítkem a vyberte **Vložit fragment**.  
  
     Zobrazí se seznam dostupných fragmenty kódu XML.  
  
3.  Fragment vyberte ze seznamu pomocí myši nebo zadáním názvu fragmentu a stisknutím klávesy TAB nebo ENTER.  
  
#### <a name="to-insert-snippets-using-the-intellisense-menu"></a>Chcete-li vložit fragmenty kódu pomocí nabídky IntelliSense  
  
1.  Umístěte kurzor na místo, kam chcete vložit fragment kódu XML.  
  
2.  Z **upravit** nabídky, přejděte na příkaz **IntelliSense**a potom vyberte **Vložit fragment**.  
  
     Zobrazí se seznam dostupných fragmenty kódu XML.  
  
3.  Fragment vyberte ze seznamu pomocí myši nebo zadáním názvu fragmentu a stisknutím klávesy TAB nebo ENTER.  
  
#### <a name="to-insert-snippets-through-the-intellisense-complete-word-list"></a>Chcete-li vložit fragmenty kódu pomocí seznamu dokončení Word IntelliSense  
  
1.  Umístěte kurzor na místo, kam chcete vložit fragment kódu XML.  
  
2.  Začněte psát fragment kódu XML, který chcete přidat do souboru. Pokud je zapnutá funkce automatického dokončování, se zobrazí seznam dokončení slov IntelliSense. Pokud se nezobrazí, stiskněte kombinaci kláves CTRL + MEZERNÍK aktivovat.  
  
3.  Vyberte ze seznamu dokončení word fragment kódu XML.  
  
4.  Stiskněte klávesu TAB, karta k vyvolání fragment kódu XML.  
  
> [!NOTE]
>  Můžou nastat případy při získání vyvolání není fragment kódu XML. Například pokud se pokusíte vložit `xs:complexType` element uvnitř `xs:element` uzlu editoru negeneruje fragmentu kódu XML. Když `xs:complexType` element se používá v `xs:element` uzlu, nejsou žádné povinné atributy dílčí prvky, takže editoru nemá žádná data k vložení.  
  
#### <a name="to-insert-snippets-using-the-shortcut-name"></a>Chcete-li vložit fragmenty kódu pomocí názvu odkazu  
  
1.  Umístěte kurzor na místo, kam chcete vložit fragment kódu XML.  
  
2.  Typ `<` v podokně editor.  
  
3.  Stisknutím klávesy ESC zavřete seznamu dokončení word IntelliSense.  
  
4.  Zadejte název zástupce fragmentu a stiskněte klávesu TAB k vyvolání fragment kódu XML.  
  
## <a name="surround-with"></a>Obklopit fragmentem  
 Následující postupy popisují, jak získat přístup **příkazu Obklopit s** příkaz.  
  
> [!NOTE]
>  **Příkazu Obklopit s** příkaz je také k dispozici prostřednictvím klávesové zkratky (CTRL + K, pak CTRL + S).  
  
#### <a name="to-use-surround-with-from-the-context-menu"></a>Použití příkazu Obklopit s z místní nabídky  
  
1.  Vyberte text, který má obklopit v editoru XML.  
  
2.  Klikněte pravým tlačítkem a vyberte **příkazu Obklopit s**.  
  
     Zobrazí se seznam dostupných okolí s fragmenty kódu XML.  
  
3.  Fragment vyberte ze seznamu pomocí myši nebo zadáním názvu fragmentu a stisknutím klávesy TAB nebo ENTER.  
  
#### <a name="to-use-surround-with-from-the-intellisense-menu"></a>Použití příkazu Obklopit s z nabídky Intellisense  
  
1.  Vyberte text, který má obklopit v editoru XML.  
  
2.  Z **upravit** nabídky, přejděte na příkaz **IntelliSense**a potom vyberte **příkazu Obklopit s**.  
  
     Zobrazí se seznam dostupných okolí s fragmenty kódu XML.  
  
3.  Fragment vyberte ze seznamu pomocí myši nebo zadáním názvu fragmentu a stisknutím klávesy TAB nebo ENTER.  
  
## <a name="using-xml-snippets"></a>Použití fragmentů kódu XML  
 Jakmile vyberete fragmentu kódu XML, se automaticky vloží text fragmentu kódu na pozici kurzoru. Jsou vyznačené všechna upravitelné pole v tomto fragmentu kódu a je automaticky vybrána první upravitelné pole. Aktuálně vybrané pole je zabalená.  
  
 Pokud je vybraná pole, můžete zadat novou hodnotu pro pole. Stisknutím karta cykly prostřednictvím upravitelné pole fragmentu; Stisknutím kláves SHIFT + TAB procházení je v obráceném pořadí. Kliknutím na pole umístí kurzor v poli a dvakrát klikněte na pole vybere. Pokud pole zvýrazní, popisek mohou být zobrazeny, nabídky popis pole.  
  
 Pouze první instance dané pole lze upravit. Když toto pole je zvýrazní, jsou uvedeny další instance tohoto pole. Když změníte hodnotu upravitelné pole, je toto pole změnit všude, kde se používá v tomto fragmentu kódu.  
  
 Stisknutím klávesy ENTER nebo ESC zruší úpravy pole a vrátí editoru normálně.  
  
 Výchozí barvy pro upravovat kód fragment kódu pole lze změnit úpravou nastavení pole fragmentu kódu **písma a barev** podokně **možnost**dialogové okno s. Další informace najdete v tématu [postupy: Změna písma a barev v editoru](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md).  
  
## <a name="see-also"></a>Viz také  
 [Fragmenty kódu XML](../xml-tools/xml-snippets.md)   
 [Postupy: generování fragmentu kódu XML z schématu XML](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)   
 [Postupy: vytvoření fragmenty kódu XML](../xml-tools/how-to-create-xml-snippets.md)