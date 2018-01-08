---
redirect_url: /visualstudio/csharp-ide/refactoring/encapsulate-field
title: "Refaktoring (C#) pro zapouzdření polí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: CSharp
helpviewer_keywords:
- Encapsulate Field refactoring operation [C#]
- refactoring [C#], Encapsulate Field
ms.assetid: bf714a04-ab1e-49ce-99ce-dda1ebb1a17f
caps.latest.revision: "26"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: d587edebcea443e0bfff52004b128c70923470d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="encapsulate-field-refactoring-c"></a>Refaktoring pro zapouzdření polí (C#)
**Zapouzdření pole** operace refaktoringu umožňuje rychle vytvořit vlastnosti z existující pole a bezproblémově aktualizace kódu s odkazy na novou vlastnost.  
  
 Když [pole](/dotnet/csharp/programming-guide/classes-and-structs/fields) je [veřejné](/dotnet/csharp/language-reference/keywords/public), jiné objekty mít přímý přístup do tohoto pole a jeho nebyla rozpoznána objektem, který vlastní toto pole můžete upravit. Pomocí [vlastnosti](/dotnet/csharp/programming-guide/classes-and-structs/properties) pro zapouzdření toto pole, zakážete přímý přístup do pole.  
  
 Chcete-li vytvořit novou vlastnost **zapouzdření pole** operace změny – modifikátor přístupu pole, která chcete k zapouzdření [privátní](/dotnet/csharp/language-reference/keywords/private)a poté generuje [získat](/dotnet/csharp/language-reference/keywords/get)a [nastavit](/dotnet/csharp/language-reference/keywords/set) přístupových objektů pro toto pole. V některých případech pouze `get` generován přistupujícího objektu, například když je deklarovaná pole jen pro čtení.  
  
 Modul refaktoringu aktualizace kódu s odkazy na nové vlastnosti v oblasti určené v **aktualizace odkazy** části **zapouzdření pole** dialogové okno.  
  
### <a name="to-create-a-property-from-a-field"></a>K vytvoření vlastnosti z pole  
  
1.  Vytvořte konzolovou aplikaci s názvem `EncapsulateFieldExample`a potom můžete nahradit `Program` s následující příklad kódu.  
  
    ```csharp  
    class Square  
    {  
        // Select the word 'width' and then use Encapsulate Field.  
        public int width, height;  
    }  
    class MainClass  
    {  
        public static void Main()  
        {  
            Square mySquare = new Square();  
            mySquare.width = 110;  
            mySquare.height = 150;  
            // Output values for width and height.  
            Console.WriteLine("width = {0}", mySquare.width);  
            Console.WriteLine("height = {0}", mySquare.height);  
        }  
    }  
    ```  
  
2.  V [Editor kódu](../ide/writing-code-in-the-code-and-text-editor.md), umístěte kurzor v deklaraci na název pole, které má být zapouzdřena. V následujícím příkladu, umístěte kurzor na slovo `width`:  
  
    ```csharp  
    public int width, height;  
    ```  
  
3.  Na **Refaktorovat** nabídky, klikněte na tlačítko **zapouzdření pole**.  
  
     **Zapouzdření pole** zobrazí se dialogové okno.  
  
     Můžete také zadat klávesovou zkratku CTRL + R E zobrazíte **zapouzdření pole** dialogové okno.  
  
     Můžete také kliknout pravým tlačítkem kurzor, přejděte na příkaz **Refaktorovat**a potom klikněte na **zapouzdření pole** zobrazíte **zapouzdření pole** dialogové okno.  
  
4.  Zadejte nastavení.  
  
5.  Stiskněte klávesu ENTER, nebo klikněte na **OK** tlačítko.  
  
6.  Pokud jste vybrali **zobrazení náhledu změn odkaz** možnost, pak se **zobrazení náhledu změn odkaz** otevře se okno. Klikněte **použít** tlačítko.  
  
     Následující `get` a `set` přístupového kódu se zobrazí ve zdrojovém souboru:  
  
    ```csharp  
    public int Width  
    {  
        get { return width; }  
        set { width = value; }  
    }  
    ```  
  
     Kód `Main` metoda je rovněž aktualizováno pro nové `Width` název vlastnosti.  
  
    ```csharp  
    Square mySquare = new Square();  
    mySquare.Width = 110;  
    mySquare.height = 150;  
    // Output values for width and height.  
    Console.WriteLine("width = {0}", mySquare.Width);  
    ```  
  
## <a name="remarks"></a>Poznámky  
 **Zapouzdření pole** operaci je možné pouze při kurzor je nastavený na stejném řádku jako deklaraci pole.  
  
 Pro deklarace, které deklarovat několik polí **zapouzdření pole** používá čárkou jako hranice mezi poli a zahájí refaktoring na pole, které je nejblíže kurzor a na stejném řádku jako kurzor. Můžete také zadat které pole, které chcete zapouzdření výběrem název tohoto pole v deklaraci.  
  
 Kód, který je generovaný této operace refaktoringu je modelovaná funkci fragmenty kódu encapsulate pole. Fragmenty kódu jsou změn. Další informace najdete v tématu [fragmenty kódu](../ide/visual-csharp-code-snippets.md).  
  
## <a name="see-also"></a>Viz také  
 [Refaktoring (C#)](refactoring-csharp.md)   
 [Fragmenty kódu v jazyce Visual C#](../ide/visual-csharp-code-snippets.md)