---
title: Používání seznamu úloh
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
ms.openlocfilehash: 3a0fb071186d816e852c695ffe1cceed29d23ff8
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="using-the-task-list"></a>Používání seznamu úloh

Použít **seznam úkolů** sledovat komentáře kódu, které používají tokeny, jako `TODO` a `HACK`, nebo vlastní tokeny a ke správě zkratky, které přejdete přímo na předdefinované umístění v kódu. Kliknutím na položku v seznamu a přejděte do umístění ve zdrojovém kódu.

## <a name="the-task-list-window"></a>Okno Seznam úkolů

Když **seznam úkolů** je otevřené, zobrazí se v dolní části okna aplikace.

### <a name="to-open-the-task-list"></a>Otevření seznamu úkolů

- Na **zobrazení** nabídce zvolte **seznam úkolů** (klávesové: Ctrl +\\, T).

    ![Okno seznam úloh](../ide/media/vs2015_task_list.png "vs2015_task_list")

### <a name="to-change-the-sort-order-of-the-list"></a>Změna pořadí řazení seznamu

- Klikněte na záhlaví libovolného sloupce. Chcete-li dále zpřesnit výsledky hledání, stiskněte klávesu Shift a klikněte na druhé záhlaví sloupce.

     Jako alternativu v místní nabídce vyberte **seřadit**a vyberte záhlaví. Chcete-li dále zpřesnit výsledky hledání, stiskněte klávesu Shift a klikněte na druhé záhlaví.

### <a name="to-show-or-hide-columns"></a>Zobrazení nebo skrytí sloupců

- V místní nabídce vyberte **zobrazit sloupce**. Vyberte sloupce, které chcete zobrazit nebo skrýt.

### <a name="to-change-the-order-of-the-columns"></a>Změna pořadí sloupců

- Přetáhněte libovolné záhlaví sloupce do požadovaného umístění.

## <a name="user-tasks"></a>Úlohy uživatele

Funkci úloh uživatele byla odebrána od ve Visual Studiu 2015. Když otevřete řešení, která má úloha dat uživatele z Visual Studio 2013 a dříve, úloha dat uživatele v souboru .suo nebude mít vliv, ale uživatelských úloh se nezobrazí v seznamu úkolů.

Pokud chcete nadále používat a aktualizovat uživatelská data úloh, by měl otevřete projekt v sadě Visual Studio 2013 a zkopírujte obsah všechny uživatele úlohy do vaší upřednostňované projektu nástroje pro správu (například Team Foundation Server).

## <a name="tokens-and-comments"></a>Tokeny a komentáře

Komentáře v kódu před sebou značku komentáře a předdefinované token se také zobrazí v **seznam úkolů** okno. Například následující komentář jazyka C# má tři samostatné části:

- Značky poznámky (`//`)

- Token, například (`TODO`)

- Komentář (zbytek textu)

```csharp
// TODO: Load state from previously suspended application
```

Protože `TODO` je i předdefinovanou tokenu, tento komentář se zobrazí jako `TODO` úloh v seznamu.

###  <a name="customTokens"></a> Vlastní tokeny

Ve výchozím nastavení, sada Visual Studio obsahuje následující klíčová slova: HACKERSKÝ TODO, UNDONE, Poznámka. Tyto nejsou velká a malá písmena.

Nebo lze také vytvořit vlastní tokeny.

#### <a name="to-create-a-custom-token"></a>Vytvoření vlastního tokenu

1. Na **nástroje** nabídky, zvolte **možnosti**.

2. Otevřete **prostředí** složku a potom zvolte **seznam úkolů**.

     [Stránka Možnosti seznam úkolů](../ide/reference/task-list-environment-options-dialog-box.md) se zobrazí.

     ![Seznam úloh v sadě Visual Studio](../ide/media/vs2015_task_list_options.png "vs2015_task_list_options")

3. V **tokeny** kategorie v **název** textového pole zadejte název tokenu, například "chyb".

4. V **s prioritou** rozevíracího seznamu vyberte výchozí prioritu pro nový token. Vyberte **přidat** tlačítko.

###  <a name="cppComments"></a> Komentáře C++ TODO

Standardně se zobrazují komentáře C++ TODO v **seznam úkolů** okno. Toto chování, můžete změnit.

#### <a name="to-turn-off-c-todo-comments"></a>Chcete-li vypnout komentáře C++ TODO

Na **nástroje** nabídce zvolte **možnosti** > **textového editoru** > **C/C++**  >   **Zobrazení** > **výčet úlohy komentářů** a nastavte hodnotu na hodnotu false.

## <a name="shortcuts"></a>Zástupci

A *zástupce* je záložek v kódu sledované **seznam úkolů**; má vlastní ikonu než regulární záložku. Dvakrát klikněte na zástupce ve **seznam úkolů** přejít na odpovídající umístění v kódu.

![Ikonu zástupce seznamu úkolů sady Visual Studio](../ide/media/vs2015_task_list_bookmark.png "vs2015_task_list_bookmark")

### <a name="to-create-a-shortcut"></a>Vytvoření zástupce

K vytvoření zástupce, vložte do kódu, kam chcete umístit zástupce ukazatele. Zvolte **upravit** > **záložky** > **přidat zástupce seznamu úkolů** nebo stiskněte klávesu **Ctrl**  +  **Tisíc**, **Ctrl** + **H**.

Procházet zástupce v kódu, zvolte zástupce v seznamu a pak zvolte **další úlohy** nebo **předchozí úloha** z místní nabídky.

## <a name="see-also"></a>Viz také

- [Dialogové okno Možnosti prostředí seznamu úloh](../ide/reference/task-list-environment-options-dialog-box.md)