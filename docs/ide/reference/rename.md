---
title: Refaktorovat a přejmenovat
ms.date: 01/26/2018
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- vs.csharp.refactoring.rename
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 2b18f5763d68487e7642f5632c05516d2f1bd9e2
ms.sourcegitcommit: aeb1a1135dd789551e15aa5124099a5fe3f0f32b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2019
ms.locfileid: "66500942"
---
# <a name="rename-a-code-symbol-refactoring"></a>Symbol kód refaktoring pro přejmenování

Tento refaktoring platí pro:

- C#

- Visual Basic

**Co:** Slouží k přejmenování identifikátory pro symboly kódu, jako je například pole lokálních proměnných, metod, obory názvů, vlastností a typy.

**Kdy:** Chcete něco bezpečně přejmenovat bez nutnosti vyhledáte všechny instance a kopírovat/vložit nový název.

**Proč:** Zkopírujete a vložíte nový název přes celý projekt by pravděpodobně vést k chybám. Tento nástroj refaktoringu přesně provede akci přejmenování.

## <a name="how-to"></a>Postupy

1. Zvýrazněte nebo umístěte kurzor textu uvnitř položky, která má být přejmenována:

   - C#:

       ![Zvýrazněný kód:C#](media/rename-highlight-cs.png)

   - Visual Basic:

       ![Zvýrazněný kód – Visual Basic](media/rename-highlight-vb.png)

2. Dále proveďte jednu z následujících akcí:

   - **Klávesnice**
      - Stisknutím klávesy **Ctrl + R**, pak **Ctrl + R**. (Všimněte si, že klávesová zkratka může být jiný platformě, na který profil vyberete.)
   - **Myši**
      - Vyberte **Upravit > Refaktorovat > přejmenujte**.
      - Klikněte pravým tlačítkem na kód a vybrat **přejmenovat**.

3. Přejmenujte položku jednoduše tak, že zadáte nový název.

   - C#:

      ![Animace – přejmenovatC#](media/rename-animated-cs.gif)

   - Visual Basic:

      ![Rename - VB](media/rename-rename-vb.png)

   > [!TIP]
   > Můžete také aktualizovat komentáře a jiných řetězců použít tento nový název, stejně jako [zobrazit náhled změn](../../ide/preview-changes.md) před uložením používání zaškrtávacích políček v **přejmenovat** pole, které se zobrazí v horní části přímo z editoru.

4. Až budete spokojení s změny, zvolte **použít** tlačítko nebo stisknutím klávesy **Enter** a změny budou potvrzeny.

## <a name="remarks"></a>Poznámky

- Pokud použijete název, který již existuje, která by způsobila konflikt, který **přejmenovat** vás upozorní pole.

   ![Přejmenovat konflikt](media/rename-conflict-cs.png)

- Dalším způsobem, jak přejmenovat symbol je můžete změnit jeho název v editoru. Stiskněte kurzor v názvu symbolu, **Ctrl**+ **.** nebo stačí rozbalte nabídku ikonu žárovky, které se zobrazí a zvolte **přejmenovat \<starý název > na \<nový název >** .

## <a name="see-also"></a>Viz také:

- [Refactoring](../refactoring-in-visual-studio.md)
- [Náhled změn](../../ide/preview-changes.md)
