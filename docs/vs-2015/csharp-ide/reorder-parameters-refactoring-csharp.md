---
title: Refaktoring přeskupení parametrů (C#) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.csharp.refactoring.reorder
dev_langs:
- CSharp
helpviewer_keywords:
- refactoring [C#], Reorder Parameters
- Reorder Parameters refactoring [C#]
ms.assetid: 4dabf21a-a9f0-41e9-b11b-55760cf2bd90
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: daf77a60256e59cabd176990f3642a2206a7f0d8
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63444549"
---
# <a name="reorder-parameters-refactoring-c"></a>Refaktoring přeskupení parametrů (C#)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Reorder Parameters` je Visual C# operace refaktoringu, která poskytuje snadný způsob, jak změnit pořadí parametrů metod, indexerů a delegátů. `Reorder Parameters` změny prohlášení, a kteroukoli lokalitou, kdy je člen volán, parametry jsou změnit jejich uspořádání tak, aby odrážely novou objednávku.  
  
 K provedení `Reorder Parameters` operace, umístěte kurzor na nebo vedle metoda, indexer nebo delegáta. Když je ukazatel myši na pozici, vyvolat `Reorder Parameters` operace stisknutím klávesové zkratky, nebo klikněte na příkaz v místní nabídce.  
  
> [!NOTE]
> První parametr metody rozšíření nemůže změnit pořadí.  
  
### <a name="to-reorder-parameters"></a>Chcete-li změnit pořadí parametrů  
  
1. Vytvoření knihovny tříd s názvem `ReorderParameters`a potom nahraďte `Class1` pomocí následujícího ukázkového kódu.  
  
    ```csharp  
    class ProtoClassA  
    {  
        // Invoke on 'MethodB'.  
        public void MethodB(int i, bool b) { }  
    }  
  
    class ProtoClassC  
    {  
        void D()  
        {  
            ProtoClassA MyClassA = new ProtoClassA();  
  
            // Invoke on 'MethodB'.  
            MyClassA.MethodB(0, false);  
        }  
    }  
    ```  
  
2. Umístěte kurzor na `MethodB`, buď v deklaraci metody nebo volání metody.  
  
3. Na **Refaktorovat** nabídky, klikněte na tlačítko **změnit uspořádání parametrů**.  
  
     **Změnit uspořádání parametrů** zobrazí se dialogové okno.  
  
4. V **změnit uspořádání parametrů** dialogu `int i` v **parametry** seznamu a potom klikněte na tlačítko dolů.  
  
     Alternativně můžete přetáhnout `int i` po `bool b` v **parametry** seznamu.  
  
5. V **změnit uspořádání parametrů** dialogové okno, klikněte na tlačítko **OK**.  
  
     Pokud **náhled změn odkazu** je vybraná možnost v **změnit uspořádání parametrů** dialogovém okně **náhled změn – Změna pořadí parametrů** se zobrazí dialogové okno. Nabízí náhled změn v seznamu parametrů pro `MethodB` v podpisu a volání metody.  
  
    1. Pokud **náhled změn – Změna pořadí parametrů** dialogové okno se zobrazí, klikněte na tlačítko **použít**.  
  
         V tomto příkladu deklarace metody a všechny metody místa pro volání `MethodB` se aktualizují.  
  
## <a name="remarks"></a>Poznámky  
 Můžete změnit pořadí parametrů v deklaraci metody nebo volání metody. Umístěte kurzor na nebo vedle deklaraci delegáta nebo metody, ale ne v těle.  
  
## <a name="see-also"></a>Viz také  
 [Refaktoring (C#)](../csharp-ide/refactoring-csharp.md)