---
title: 'Návrhář postupu provádění – jak: Používání návrháře proměnných'
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
f1_keywords:
- System.Activities.Presentation.View.DesignTimeVariable.UI
ms.assetid: 0318dfb0-bf8f-4f92-9b86-ae4c1b2161ad
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7b7df8f03444a0205c5628bbd36f249d68b43ad7
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53824338"
---
# <a name="how-to-use-the-variable-designer"></a>Postupy: Používání návrháře proměnných

Návrhář proměnných slouží k vytvoření proměnné pro použití v scénáře datových vazeb a podmíněné příkazy. Návrhář přistupuje po kliknutí **proměnné** tlačítko v levém dolním rohu návrhové plátno. Návrhář obsahuje seznam proměnných, které se zobrazí ve formě tabulky a může být řada seřazena podle všech záhlaví sloupců, s výjimkou **výchozí** sloupce. Každá proměnná obsahuje název, typ proměnné, oboru a výchozí hodnota (pokud existuje). Název a výchozí hodnotu nejsou upravitelné textové pole a typu a rozsahu jsou rozevírací seznamy. Obor je aktivita, která byla vybrána při Návrhář proměnných. Pokud proměnnou nelze vytvořit v rámci oboru výběru, bude výchozí obor na nejbližší nadřazenou aktivitou, která umožňuje proměnných vytvořené v jeho oboru výběru. Další informace najdete v tématu [proměnné a argumenty (.NET)](/dotnet/framework/windows-workflow-foundation/variables-and-arguments).

 Pořadí řazení se nepoužije, dokud uživatel explicitně používá jeden z řazení ovládacích prvků, zavře a znovu neotevře Návrhář proměnných nebo vytvoří jiné proměnné.

## <a name="to-create-a-new-variable"></a>Chcete-li vytvořit nové proměnné

1.  Otevřete řešení pracovního postupu nebo aktivity v sadě Visual Studio.

2.  Na plátně návrhu vyberte aktivitu v pracovním postupu.

3.  Otevřít návrhář proměnných kliknutím **proměnné** tlačítko v levém dolním rohu návrhové plátno. Otevře se Návrhář proměnných.

4.  Klikněte na prázdný řádek označený **vytvořit proměnnou**. Tím se přidá nový řádek pomocí nové proměnné pomocí následující výchozí hodnoty: variablex pro **název** tam, kde x je celé číslo s počáteční hodnotou 1, který je automatický navýšeno vytvořit jedinečné názvy proměnných,  **Řetězec** pro **typ proměnné**, a **pořadí** pro **oboru**. Přidá se žádná hodnota pro **výchozí**. Tyto hodnoty můžete změnit kdykoli během procesu návrhu pracovního postupu.

    > [!NOTE]
    > Pokud chcete odstranit proměnnou, kliknutím vyberte proměnnou a stiskněte klávesu **odstranit** klíč.

## <a name="see-also"></a>Viz také:

- [Používání návrháře postupu provádění](developing-applications-with-the-workflow-designer.md)
- [Proměnné a argumenty](/dotnet/framework/windows-workflow-foundation/variables-and-arguments)
- [Postupy: Používání návrháře argumentů](../workflow-designer/how-to-use-the-argument-designer.md)