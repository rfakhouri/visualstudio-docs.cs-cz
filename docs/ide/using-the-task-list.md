---
title: Použití seznamu úkolů
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- TaskListWindow
- VS.TaskList
- tasklist
helpviewer_keywords:
- task list
- Visual Studio, task list
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ffbe1b7f293bc525aa03a536c0fa4fa55ce3e82a
ms.sourcegitcommit: 3cda0d58c5cf1985122b8977b33a171c7359f324
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/29/2019
ms.locfileid: "70154861"
---
# <a name="use-the-task-list"></a>Použití seznamu úkolů

Použijte **seznam úkolů** ke sledování komentářů kódu, které používají tokeny `TODO` , `HACK`jako jsou a, nebo vlastní tokeny, a ke správě zástupců, které vás přejímají přímo na předdefinované umístění v kódu. Kliknutím na položku v seznamu přejdete do jejího umístění ve zdrojovém kódu.

> [!NOTE]
> Toto téma se vztahuje k sadě Visual Studio ve Windows. Visual Studio pro Mac najdete v tématu [Komentáře k úkolům (Visual Studio pro Mac)](/visualstudio/mac/task-comments).

## <a name="the-task-list-window"></a>Okno Seznam úkolů

Když je **seznam úkolů** otevřené, zobrazí se v dolní části okna aplikace.

Chcete-li otevřít **seznam úkolů**, vyberte možnost **Zobrazit** > **seznam úkolů**nebo na klávesnici stiskněte klávesu **CTRL**+ **\\** ,**T**.

![okno Seznam úkolů](../ide/media/vs2015_task_list.png)

Chcete-li změnit pořadí řazení seznamu, vyberte záhlaví libovolného sloupce. Chcete-li dále zpřesnit výsledky hledání, stiskněte klávesu **SHIFT** a klikněte na druhé záhlaví sloupce. Případně můžete v místní nabídce vybrat položku **Seřadit podle**a potom zvolit záhlaví. Chcete-li dále zpřesnit výsledky hledání, stiskněte klávesu **SHIFT** a zvolte druhé záhlaví.

Chcete-li zobrazit nebo skrýt sloupce, v místní nabídce vyberte možnost **Zobrazit sloupce**. Vyberte sloupce, které chcete zobrazit nebo skrýt.

Chcete-li změnit pořadí sloupců, přetáhněte libovolné záhlaví sloupce do umístění, které chcete.

## <a name="user-tasks"></a>Uživatelské úkoly

Funkce úlohy uživatele byla odebrána v aplikaci Visual Studio 2015. Když otevřete řešení, které má data úkolu uživatele z Visual Studio 2013 a dříve, nebudou ovlivněna data uživatelských úloh v souboru *. suo* , ale v seznamu úkolů se nezobrazí úkoly uživatele.

Pokud chcete pokračovat v přístupu a aktualizaci dat uživatelských úloh, otevřete projekt v Visual Studio 2013 a zkopírujte obsah všech uživatelských úloh do preferovaného nástroje pro správu projektu (například Team Foundation Server).

## <a name="tokens-and-comments"></a>Tokeny a komentáře

Komentář v kódu předchází značku komentáře a předdefinovaný token se také zobrazí v **seznam úkolů**. Například následující komentář jazyka C# má tři samostatné části:

- Značka komentáře (`//`)

- Token, například (`TODO`)

- Komentář (zbytek textu)

```csharp
// TODO: Load state from previously suspended application
```

Vzhledem `TODO` k tomu, že je předdefinovaný token, tento `TODO` komentář se zobrazí jako úkol v seznamu.

> [!NOTE]
> Výchozí tokeny jsou dostupné jenom pro jazyky CC++/ C#, a VB. Další jazyky najdete v části **vlastní tokeny** .

### <a name="custom-tokens"></a>Vlastní tokeny

Ve výchozím nastavení Visual Studio obsahuje následující tokeny: `HACK`, `TODO`, `UNDONE`a `UnresolvedMergeConflict`. Nerozlišují velká a malá písmena. Nebo lze také vytvořit vlastní tokeny.

Vytvoření vlastního tokenu:

1. Na **nástroje** nabídce zvolte **možnosti**.

2. Otevřete složku **prostředí** a zvolte možnost **seznam úkolů**.

   Zobrazí se [Stránka možnosti seznam úkolů](../ide/reference/task-list-environment-options-dialog-box.md) .

   ![Seznam úkolů sady Visual Studio](../ide/media/vs2015_task_list_options.png)

3. Do textového pole **název** zadejte název tokenu, například **Chyba**.

4. V rozevíracím seznamu **Priorita** vyberte výchozí prioritu pro nový token.

5. Zvolte **přidat**.

> [!TIP]
> Tlačítko **Přidat** se aktivuje po zadání názvu. Před kliknutím na **Přidat**je nutné zadat název.

### <a name="c-todo-comments"></a>Komentáře C++ TODO

Ve výchozím nastavení C++ se komentáře TODO zobrazují v **seznam úkolů**.

Pokud chcete komentáře C++ TODO vypnout, v nabídce **nástroje** vyberte **Možnosti** > **textový editor** >  > **C/C++** **Zobrazit** > **výčet úkolů** s komentářem. a nastavte hodnotu na **false**.

## <a name="shortcuts"></a>Zástupci

*Zástupce* je záložka v kódu, která je sledována v **seznam úkolů**. Má jinou ikonu než běžná záložka. Dvojím kliknutím na zástupce v **seznam úkolů** přejděte na odpovídající umístění v kódu.

![Ikona zástupce Seznam úkolů sady Visual Studio](../ide/media/vs2015_task_list_bookmark.png)

### <a name="create-a-shortcut"></a>Vytvoření zástupce

Chcete-li vytvořit zástupce, vložte ukazatel do kódu, kam chcete umístit zástupce. Zvolte možnost **Upravit** > **záložky**++přidat seznam úkolů zástupce nebo stiskněte klávesy CTRL K, CTRL H. > 

Chcete-li procházet zástupce v kódu, zvolte zástupce v seznamu a potom v místní nabídce zvolte možnost **Další úkol** nebo **předchozí úkol** .

## <a name="see-also"></a>Viz také:

- [Seznam úkolů, prostředí, dialogové okno Možnosti](../ide/reference/task-list-environment-options-dialog-box.md)
- [Komentáře k úkolu (Visual Studio pro Mac)](/visualstudio/mac/task-comments)
