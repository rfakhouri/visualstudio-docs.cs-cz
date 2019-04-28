---
title: 'Postupy: Ukládání a upravování připojovacích řetězců'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f8ef3a2c-029c-423b-9d9e-a4f1add4f640
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 1f8300043f9a16c7d92d72c4dcb22e4cd0432a06
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62566968"
---
# <a name="how-to-save-and-edit-connection-strings"></a>Postupy: Uložení a úpravy připojovacích řetězců
Připojovací řetězce v aplikacích Visual Studio jsou uložené v konfiguračním souboru aplikace (také označované jako nastavení aplikace) nebo pevně zakódované přímo ve vaší aplikaci. Ukládání připojovacích řetězců v konfiguračním souboru aplikace zjednodušuje úlohu údržbu aplikace. Pokud je potřeba změnit připojovací řetězec, můžete ho aktualizovat v souboru nastavení aplikace (na rozdíl od nutnosti změna ve zdrojovém kódu a znovu zkompilovat aplikaci).

Ukládání citlivých informací (například heslo) v rámci připojovací řetězec může ovlivnit zabezpečení aplikace. Připojovací řetězce, které jsou uloženy do konfiguračního souboru aplikace není zašifrované nebo obfuskovaný, takže je možné pro uživatele pro přístup k souboru a zobrazit jeho obsah. Použití integrované zabezpečení Windows je bezpečnější způsob řízení přístupu k databázi.

Pokud nevyberete použít integrované zabezpečení Windows a vaše databáze vyžaduje uživatelské jméno a heslo, můžete je vynechat z připojovacího řetězce, ale vaše aplikace bude muset zadat tyto informace se úspěšně připojit k databázi. Můžete například vytvořit dialogové okno, které se zobrazí výzva pro tyto informace a dynamicky vytvoří řetězec připojení v době běhu. Zabezpečení stále může být problém, pokud je na cestě k databázi informace.
Další informace najdete v tématu [ochrana informací o připojení](/dotnet/framework/data/adonet/protecting-connection-information).

## <a name="to-save-a-connection-string-from-within-the-data-source-configuration-wizard"></a>Chcete-li uložit připojovací řetězec z v rámci Průvodce konfigurací zdroje dat
V **Průvodce konfigurací zdroje dat**, vyberte možnost uložit připojení **uložit připojovací řetězec do konfiguračního souboru aplikace** stránky.

## <a name="to-save-a-connection-string-directly-into-application-settings"></a>Chcete-li uložit připojovací řetězec přímo do nastavení aplikace
1. V **Průzkumníku řešení**, dvakrát klikněte **Můj projekt** ikonu (Visual Basic) nebo **vlastnosti** ikonu (C#) otevřete **Návrháře projektu**.
1. Vyberte **nastavení** kartu.
1. Zadejte **název** pro připojovací řetězec. Při přístupu k připojovací řetězec v kódu odkazovat na tento název.
1. Nastavte **typ** k (**připojovací řetězec**).
1. Nechte **oboru** nastavena na **aplikace**.
1. Zadejte připojovací řetězec do **hodnotu** pole nebo klikněte na tlačítko **tlačítko se třemi tečkami** tlačítko (...) v **hodnotu** pole, které chcete otevřít **vlastnosti připojení** dialogové okno k sestavení připojovacího řetězce.

## <a name="edit-connection-strings-stored-in-application-settings"></a>Upravit připojovací řetězce, které jsou uložené v nastavení aplikace
Můžete upravit informace o připojení, který je uložen v nastavení aplikace s použitím **Návrháře projektu**.

### <a name="to-edit-a-connection-string-stored-in-application-settings"></a>Chcete-li upravit připojovací řetězec uložen v nastavení aplikace
1. V **Průzkumníku řešení**, dvakrát klikněte **Můj projekt** ikonu (Visual Basic) nebo **vlastnosti** ikonu (C#) otevřete **Návrháře projektu**.
1. Vyberte **nastavení** kartu.
1. Najděte připojení, které chcete upravit a vybrat text **hodnotu** pole.
1. Upravit připojovací řetězec **hodnotu** pole nebo klikněte na tlačítko **tlačítko se třemi tečkami** tlačítko (...) v **hodnotu** pole, které chcete upravit připojení k **připojení Vlastnosti** dialogové okno.

## <a name="edit-connection-strings-for-datasets"></a>Upravit připojovací řetězce pro datové sady
Můžete upravit informace o připojení pro každý TableAdapter v datové sadě.

### <a name="to-edit-a-connection-string-for-a-tableadapter-in-a-dataset"></a>Chcete-li upravit připojovací řetězec pro TableAdapter v datové sadě
1. V **Průzkumníka řešení**, dvakrát klikněte datovou sadu (**XSD** souboru), který má připojení, které chcete upravit.
1. Vyberte **TableAdapter** nebo dotaz, který má připojení, které chcete upravit.
1. V **vlastnosti** okna, rozbalte **uzel připojení**.
1. K rychlé úpravě připojovací řetězec, upravit **ConnectionString** vlastnost, nebo klikněte na šipku dolů na **připojení** vlastnosti a zvolte **nové připojení**.

## <a name="security"></a>Zabezpečení
Ukládání citlivých informací (například hesla) v rámci připojovací řetězec může ovlivnit zabezpečení aplikace. Použití integrované zabezpečení Windows je bezpečnější způsob řízení přístupu k databázi.
Další informace najdete v tématu [ochrana informací o připojení](/dotnet/framework/data/adonet/protecting-connection-information).

## <a name="see-also"></a>Viz také:

- [Přidání připojení](../data-tools/add-new-connections.md)