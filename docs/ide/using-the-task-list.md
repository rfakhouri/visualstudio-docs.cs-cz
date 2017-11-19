---
title: "Používání seznamu úkolů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TaskListWindow
- VS.TaskList
- tasklist
helpviewer_keywords:
- task list
- Visual Studio, task list
ms.assetid: f46a75a8-47b3-4cb6-bb59-b72e3356a664
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a380d0e1503a0a0a0683d6088a1ca2f9c085184d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="using-the-task-list"></a>Používání seznamu úloh
Použít **seznam úkolů** sledovat komentáře kódu, které používají tokeny, jako `TODO` a `HACK`, nebo vlastní tokeny a ke správě zkratky, které přejdete přímo na předdefinované umístění v kódu. Kliknutím na položku v seznamu a přejděte do umístění ve zdrojovém kódu.  
  
 V tomto tématu:  
  
-   [Okno seznam úloh](../ide/using-the-task-list.md#taskListWindow)  
  
-   [Úlohy uživatele](../ide/using-the-task-list.md#userTasks)  
  
-   [Tokeny a komentáře](../ide/using-the-task-list.md#tokensComments)  
  
-   [Vlastní tokeny](../ide/using-the-task-list.md#customTokens)  
  
-   [Komentáře C++ TODO](../ide/using-the-task-list.md#cppComments)  
  
-   [Zkratky](../ide/using-the-task-list.md#shortcuts)  
  
##  <a name="taskListWindow"></a>Okno seznam úloh  
 Když **seznam úkolů** je otevřené, zobrazí se v dolní části okna aplikace.  
  
#### <a name="to-open-the-task-list"></a>Otevření seznamu úkolů  
  
-   Na **zobrazení** nabídce zvolte **seznam úkolů** (klávesové: Ctrl +\\, T).  
  
     ![Okno seznam úloh](../ide/media/vs2015_task_list.png "vs2015_task_list")  
  
#### <a name="to-change-the-sort-order-of-the-list"></a>Změna pořadí řazení seznamu  
  
-   Klikněte na záhlaví libovolného sloupce. Chcete-li dále zpřesnit výsledky hledání, stiskněte klávesu Shift a klikněte na druhé záhlaví sloupce.  
  
     Jako alternativu v místní nabídce vyberte **seřadit**a vyberte záhlaví. Chcete-li dále zpřesnit výsledky hledání, stiskněte klávesu Shift a klikněte na druhé záhlaví.  
  
#### <a name="to-show-or-hide-columns"></a>Zobrazení nebo skrytí sloupců  
  
-   V místní nabídce vyberte **zobrazit sloupce**. Vyberte sloupce, které chcete zobrazit nebo skrýt.  
  
#### <a name="to-change-the-order-of-the-columns"></a>Změna pořadí sloupců  
  
-   Přetáhněte libovolné záhlaví sloupce do požadovaného umístění.  
  
##  <a name="userTasks"></a>Úlohy uživatele  
 Odebrali jsme funkci uživatele úloh v sadě Visual Studio 2015. Když otevřete řešení, která má úloha dat uživatele z Visual Studio 2013 a dříve v sadě Visual Studio 2015, nebude mít vliv úloh dat uživatele v souboru .suo, ale uživatelských úloh se nezobrazí v seznamu úkolů.  
  
 Pokud chcete nadále používat a aktualizovat uživatelská data úloh, by měl otevřete projekt v sadě Visual Studio 2013 a zkopírujte obsah všechny uživatele úlohy do vaší upřednostňované projektu nástroje pro správu (například Team Foundation Server).  
  
##  <a name="tokensComments"></a>Tokeny a komentáře  
 Komentáře v kódu před sebou značku komentáře a předdefinované token se také zobrazí v **seznam úkolů** okno. Například následující komentář jazyka C# má tři samostatné části:  
  
-   Značky poznámky (`//`)  
  
-   Token, například (`TODO`)  
  
-   Komentář (zbytek textu)  
  
```  
// TODO: Load state from previously suspended application  
```  
  
 Protože `TODO` je i předdefinovanou tokenu, tento komentář se zobrazí jako `TODO` úloh v seznamu.  
  
###  <a name="customTokens"></a>Vlastní tokeny  
 Ve výchozím nastavení, sada Visual Studio obsahuje následující klíčová slova: HACKERSKÝ TODO, UNDONE, Poznámka. Tyto nejsou velká a malá písmena.  
  
 Nebo lze také vytvořit vlastní tokeny.  
  
##### <a name="to-create-a-custom-token"></a>Vytvoření vlastního tokenu  
  
1.  Na **nástroje** nabídky, zvolte **možnosti**.  
  
2.  Otevřete **prostředí** složku a potom zvolte **seznam úkolů**.  
  
     [Seznam úkolů, prostředí, dialogové okno Možnosti](../ide/reference/task-list-environment-options-dialog-box.md) se zobrazí.  
  
     ![Seznam úloh v sadě Visual Studio](../ide/media/vs2015_task_list_options.png "vs2015_task_list_options")  
  
3.  V **tokeny** kategorie v **název** textového pole zadejte název tokenu, například "chyb".  
  
4.  V **s prioritou** rozevíracího seznamu vyberte výchozí prioritu pro nový token. Vyberte **přidat** tlačítko.  
  
###  <a name="cppComments"></a>Komentáře C++ TODO  
 Standardně se zobrazují komentáře C++ TODO v **seznam úkolů** okno. Toto chování, můžete změnit.  
  
##### <a name="to-turn-off-c-todo-comments"></a>Chcete-li vypnout komentáře C++ TODO  
  
1.  Na **nástroje** nabídky, přejděte na **možnosti &#124; Textový Editor &#124; C/C++ &#124; Zobrazit &#124; Zobrazení výčtu úloh komentář** a nastavte hodnotu na hodnotu false.  
  
2.  V **možnosti** dialogové okno, otevřete **textového editoru**.  
  
3.  V části **C/C++**, zvolte **zobrazení**a poté nastavte **výčet úlohy komentářů** k **False**.  
  
##  <a name="shortcuts"></a>Zkratky  
 A *zástupce* je záložek v kódu sledované **seznam úkolů**; má vlastní ikonu než regulární záložku. Dvakrát klikněte na zástupce ve **seznam úkolů** přejít na odpovídající umístění v kódu.  
  
 ![Ikonu zástupce seznamu úkolů sady Visual Studio](../ide/media/vs2015_task_list_bookmark.png "vs2015_task_list_bookmark")  
  
#### <a name="to-create-a-shortcut"></a>Vytvoření zástupce  
  
-   Umístěte ukazatel myši do kódu tam, kde chcete zástupce vložit. Zvolte **Upravit &#124; Záložky &#124; Přidat zástupce seznamu úkolů** nebo stiskněte klávesu (klávesové: Ctrl + K, Ctrl + H).  
  
     Procházet zástupce v kódu, zvolte zástupce v seznamu a pak zvolte **další úlohy** nebo **předchozí úloha** z místní nabídky.  
  
## <a name="see-also"></a>Viz také  
 [Dialogové okno Možnosti prostředí seznamu úloh](../ide/reference/task-list-environment-options-dialog-box.md)