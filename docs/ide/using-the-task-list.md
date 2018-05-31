---
title: Použití seznamu úloh
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46a156e7f016c0966321240f5ae2362f2bc161e7
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/19/2018
ms.locfileid: "34336068"
---
# <a name="use-the-task-list"></a>Použití seznamu úloh

Použít **seznam úkolů** sledovat komentáře kódu, které používají tokeny, jako `TODO` a `HACK`, nebo vlastní tokeny a ke správě zkratky, které můžete přejít přímo na předdefinované umístění v kódu. Kliknutím na položku v seznamu a přejděte do umístění ve zdrojovém kódu.

## <a name="the-task-list-window"></a>Okno Seznam úkolů

Když **seznam úkolů** je otevřené, zobrazí se v dolní části okna aplikace.

Chcete-li otevřít **seznam úkolů**, vyberte **zobrazení** > **seznam úkolů**, nebo z klávesnici stiskněte klávesu **Ctrl** + **\\**,**T**.

![okno Seznam úkolů](../ide/media/vs2015_task_list.png)

Chcete-li změnit pořadí řazení seznamu, vyberte na záhlaví libovolného sloupce. Pro další upřesnění výsledky hledání, stiskněte klávesu **Shift** a klikněte na druhý záhlaví sloupce. Nebo v místní nabídce zvolte **seřadit**a potom vyberte záhlaví. Pro další upřesnění výsledky hledání, stiskněte klávesu **Shift** a vyberte druhý záhlaví.

Chcete-li zobrazit nebo skrýt sloupce v místní nabídce zvolte **zobrazit sloupce**. Vyberte sloupce, které chcete zobrazit nebo skrýt.

Chcete-li změnit pořadí sloupců, přetáhněte záhlaví všechny sloupce do umístění, které chcete.

## <a name="user-tasks"></a>Uživatelské úkoly

Funkce úkolů uživatele byla odebrána v sadě Visual Studio 2015. Když otevřete řešení, které má uživatel úloh data ze sady Visual Studio 2013 a starší, uživatel úkolů dat ve vaší *.suo* soubor nemá vliv, ale uživatel úlohy se nezobrazují v seznamu úkolů.

Pokud chcete nadále přístup a aktualizovat uživatelská data úloh, otevřete projekt v sadě Visual Studio 2013 a zkopírujte obsah všech uživatelských úloh do vaší upřednostňované projektu nástroje pro správu (například Team Foundation Server).

## <a name="tokens-and-comments"></a>Tokeny a komentáře

Komentáře v kódu před sebou značku komentáře a předdefinované token se zobrazí také v **seznam úkolů**. Například následující komentář jazyka C# má tři samostatné části:

- Značky poznámky (`//`)

- Token, například (`TODO`)

- Komentář (zbytek textu)

```csharp
// TODO: Load state from previously suspended application
```

Protože `TODO` je i předdefinovanou tokenu, tento komentář se zobrazí jako `TODO` úloh v seznamu.

### <a name="custom-tokens"></a>Vlastní tokeny

Ve výchozím nastavení, sada Visual Studio obsahuje následující klíčová slova: `HACK`, `TODO`, `UNDONE`, a `NOTE`. Nejsou malá a velká písmena.

Nebo lze také vytvořit vlastní tokeny. Vytvoření vlastního tokenu:

1. Na **nástroje** nabídky, zvolte **možnosti**.

2. Otevřete **prostředí** složku a potom zvolte **seznam úkolů**.

   [Stránka Možnosti seznam úkolů](../ide/reference/task-list-environment-options-dialog-box.md) se zobrazí.

   ![Seznam úloh v sadě Visual Studio](../ide/media/vs2015_task_list_options.png)

3. V **tokeny** kategorie v **název** text například zadejte název tokenu **chyb**.

4. V **s prioritou** rozevíracího seznamu vyberte výchozí prioritu pro nový token. Vyberte **přidat** tlačítko.

### <a name="c-todo-comments"></a>Komentáře C++ TODO

Ve výchozím nastavení, komentáře C++ TODO se zobrazí v **seznam úkolů**.

Chcete-li vypnout komentáře C++ TODO na **nástroje** nabídce zvolte **možnosti** > **textového editoru** > **C/C++**  >  **Zobrazení** > **výčet úlohy komentářů**a nastavte hodnotu na **false**.

## <a name="shortcuts"></a>Zástupci

A *zástupce* je záložek v kódu, který je sledovány v **seznam úkolů**. Má vlastní ikonu než regulární záložku. Dvakrát klikněte na zástupce v **seznam úkolů** přejít na odpovídající umístění v kódu.

![Ikonu zástupce seznamu úkolů sady Visual Studio](../ide/media/vs2015_task_list_bookmark.png)

### <a name="create-a-shortcut"></a>Vytvořte zástupce

K vytvoření zástupce, vložte do kódu, kam chcete umístit zástupce ukazatele. Zvolte **upravit** > **záložky** > **přidat zástupce seznamu úkolů** nebo stiskněte klávesu **Ctrl** + **Tisíc**, **Ctrl**+**H**.

Procházet zástupce v kódu, zvolte zástupce v seznamu a pak zvolte **další úlohy** nebo **předchozí úloha** z místní nabídky.

## <a name="see-also"></a>Viz také

- [Úloha seznamu, prostředí, dialogové okno Možnosti](../ide/reference/task-list-environment-options-dialog-box.md)