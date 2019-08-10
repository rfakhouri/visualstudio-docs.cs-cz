---
title: 'Postupy: Přidání nebo odebrání importovaných oborů názvů (Visual Basic)'
ms.date: 06/21/2017
ms.topic: conceptual
helpviewer_keywords:
- adding imported namespaces
- removing imported namespaces
- namespaces [Visual Studio], imported
- imported namespaces [Visual Studio]
- references [Visual Studio], imported namespaces
ms.assetid: 44cebec3-0ea0-47c2-8406-4edeab6a997e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c443f966265f70a729e2fd433353c4856a1f8c6
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68924053"
---
# <a name="how-to-add-or-remove-imported-namespaces-visual-basic"></a>Postupy: Přidání nebo odebrání importovaných oborů názvů (Visual Basic)

Import oboru názvů umožňuje použít prvky z tohoto oboru názvů ve vašem kódu bez úplného zařazení prvku. Například pokud `Create` chcete získat přístup k metodě `System.Messaging.MessageQueue` ve třídě `System.Messaging` , můžete importovat obor názvů a pouze odkazovat na prvek, který potřebujete v kódu jako `MessageQueue.Create`.

Importované obory názvů jsou spravovány na stránce **odkazy** v **Návrháři projektu**. Importy, které zadáte v tomto dialogovém okně, jsou předány přímo kompilátoru ( */Imports*) a platí pro všechny soubory v projektu. `Imports` Použijte příkaz pro použití oboru názvů v jednom souboru zdrojového kódu.

### <a name="to-add-an-imported-namespace"></a>Přidání importovaného oboru názvů

1. V **Průzkumník řešení**dvakrát klikněte na uzel **můj projekt** pro projekt.

2. V **Návrháři projektu**klikněte na kartu **odkazy** .

3. V seznamu **importované obory názvů** zaškrtněte políčko pro obor názvů, který chcete přidat.

    > [!NOTE]
    > Aby bylo možné importovat, musí být obor názvů v odkazované součásti. Pokud se obor názvů v seznamu nezobrazí, budete muset přidat odkaz na komponentu, která ho obsahuje. Další informace najdete v tématu [Správa odkazů v projektu](managing-references-in-a-project.md).

### <a name="to-remove-an-imported-namespace"></a>Odebrání importovaného oboru názvů

1. V **Průzkumník řešení**dvakrát klikněte na uzel **můj projekt** pro projekt.

2. V **Návrháři projektu**klikněte na kartu **odkazy** .

3. V seznamu **importované obory názvů** zrušte zaškrtnutí políčka pro obor názvů, který chcete odebrat.

## <a name="user-imports"></a>Importy uživatelů
Importy uživatelů umožňují importovat konkrétní třídu v rámci oboru názvů, nikoli celý obor názvů. Například vaše aplikace může mít import pro <xref:System.Diagnostics> obor názvů, ale jediná třída v rámci tohoto oboru názvů, které vás zajímá, `Debug` je třída. Můžete definovat <xref:System.Diagnostics.Debug> jako import uživatele a pak odebrat import pro <xref:System.Diagnostics>.

Pokud se později rozhodnete, že jste si sami mysleli `EventLog` , že skutečně jste potřebovali, můžete <xref:System.Diagnostics.EventLog> zadat jako import a přepsat <xref:System.Diagnostics.Debug> uživatele pomocí funkce aktualizace.

### <a name="to-add-a-user-import"></a>Přidání importu uživatele

1. V **Průzkumník řešení**dvakrát klikněte na uzel **můj projekt** pro projekt.

2. V **Návrháři projektu**klikněte na kartu **odkazy** .

3. Do textového pole pod seznamem **importované obory názvů** zadejte úplný název oboru názvů, který chcete importovat, včetně kořenového oboru názvů.

4. Kliknutím na tlačítko **Přidat import uživatele** přidejte obor názvů do seznamu **importovaných oborů názvů** .

    > [!NOTE]
    > Tlačítko **Přidat uživatelský import** bude zakázáno, pokud obor názvů odpovídá jednomu, který je již v seznamu. Import nemůžete přidat dvakrát.

### <a name="to-update-a-user-import"></a>Aktualizace importu uživatelů

1. V **Průzkumník řešení**dvakrát klikněte na uzel **můj projekt** pro projekt.

2. V **Návrháři projektu**klikněte na kartu **odkazy** .

3. V seznamu **importované obory názvů** vyberte obor názvů, který chcete změnit.

4. Do textového pole pod seznamem **importované obory názvů** zadejte název nového oboru názvů.

5. Kliknutím na tlačítko **aktualizovat import uživatele** aktualizujete obor názvů v seznamu **importovaných oborů názvů** .

## <a name="see-also"></a>Viz také:

- [Správa odkazů v projektu](../ide/managing-references-in-a-project.md)