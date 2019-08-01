---
title: Akce sestavení pro soubory
ms.date: 11/19/2018
ms.technology: vs-ide-compile
ms.topic: reference
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 061a3cce8d1d29b57c02de4506a809994bf12910
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416497"
---
# <a name="build-actions"></a>Akce sestavení

Všechny soubory v projektu sady Visual Studio mají akci sestavení. Akce sestavení Určuje, co se stane se souborem při kompilování projektu.

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac najdete v tématu [Akce sestavení v Visual Studio pro Mac](/visualstudio/mac/build-actions).

## <a name="set-a-build-action"></a>Nastavit akci sestavení

Chcete-li nastavit akci sestavení pro soubor, otevřete vlastnosti souboru v okně **vlastnosti** tak, že vyberete soubor v **Průzkumník řešení** a stisknete klávesu **ALT**+**ENTER**. Nebo klikněte pravým tlačítkem na soubor v **Průzkumník řešení** a vyberte **vlastnosti**. V okně **vlastnosti** v části Upřesnit použijte rozevírací seznam vedle **Možnosti** **sestavit akci** pro nastavení akce sestavení pro daný soubor.

![Akce sestavení pro soubor v aplikaci Visual Studio](media/build-actions.png)

## <a name="build-action-values"></a>Sestavit hodnoty akcí

Některé akce sestavení pro C# a Visual Basic soubory projektu jsou:

* **Žádné** – soubor není součástí sestavení jakýmkoli způsobem. Tato hodnota se dá použít například pro soubory dokumentace, například soubory Readme.
* **Kompilovat** – soubor je předán kompilátoru jako zdrojový soubor.
* **Obsah** – soubor označený jako **obsah** lze načíst jako datový proud voláním <xref:System.Windows.Application.GetContentStream%2A?displayProperty=nameWithType>. Pro projekty ASP.NET jsou tyto soubory zahrnuty jako součást webu při jeho nasazení.
* **Vložený prostředek** – soubor se předává kompilátoru jako prostředek, který se má vložit do sestavení. Můžete zavolat <xref:System.Reflection.Assembly.GetManifestResourceStream%2A?displayProperty=fullName> pro čtení souboru ze sestavení.
* **AdditionalFiles** – nezdrojový textový soubor, který se předává do kompilátoru C# nebo Visual Basic jako vstup. Tato akce sestavení slouží hlavně k poskytnutí vstupů [analyzátorům](../code-quality/roslyn-analyzers-overview.md) , na které se odkazuje v projektu za účelem ověření kvality kódu. Další informace najdete v tématu [použití dalších souborů](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Using%20Additional%20Files.md).

## <a name="see-also"></a>Viz také:

- [Možnosti kompilátoru jazyka C#](/dotnet/csharp/language-reference/compiler-options/listed-alphabetically)
- [Možnosti kompilátoru Visual Basic](/dotnet/visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically)
- [Akce sestavení (Visual Studio pro Mac)](/visualstudio/mac/build-actions)