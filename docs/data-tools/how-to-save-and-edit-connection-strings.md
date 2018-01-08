---
title: "Postupy: ukládání a upravování připojovacích řetězců | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8ef3a2c-029c-423b-9d9e-a4f1add4f640
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: bb3ddcf8a4d1ac14b356bfabac2378ff345ef65b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-save-and-edit-connection-strings"></a>Postupy: Ukládání a upravování připojovacích řetězců
Připojovací řetězce v sadě Visual Studio aplikace můžete uložit v konfiguračním souboru aplikace (také označované jako nastavení aplikace) nebo pevně přímo v aplikaci. Ukládání připojovacích řetězců v konfiguračním souboru aplikace zjednodušuje správu vaší aplikace. Pokud je potřeba změnit připojovací řetězec, můžete ho aktualizovat v souboru nastavení aplikace (na rozdíl od nutnosti změnit ve zdrojovém kódu a překompilování aplikace).

Ukládání citlivých informací (například heslo) v připojovacím řetězci může ovlivnit zabezpečení vaší aplikace. Připojovací řetězce, které jsou uloženy do konfiguračního souboru aplikace nejsou zašifrované nebo matoucí, takže je možné získat přístup k souboru a zobrazte její obsah. Pomocí integrované zabezpečení systému Windows je bezpečnější způsob, jak řídit přístup k databázi.

Pokud není rozhodnete použít integrované zabezpečení systému Windows a vaše databáze vyžaduje zadání uživatelského jména a hesla, je možné vynechat z připojovacího řetězce, ale aplikace bude vyžadovat poskytnout tyto informace se úspěšně připojit k databázi. Můžete například vytvořit dialogové okno se zobrazí výzvu pro tyto informace a dynamicky vytvoří připojovací řetězec za běhu. Zabezpečení stále může být problém, pokud je zachycen informace na cestě k databázi. Další informace najdete v tématu [chrání informace o připojení](/dotnet/framework/data/adonet/protecting-connection-information).

## <a name="to-save-a-connection-string-from-within-the-data-source-configuration-wizard"></a>Chcete-li uložit připojovacího řetězce z v rámci Průvodce konfigurací zdroje dat
V **Průvodce konfigurací zdroje dat**, vyberte možnost pro uložení připojení na Uložit připojovací řetězec na stránku konfiguračního souboru aplikace.

## <a name="to-save-a-connection-string-directly-into-application-settings"></a>Připojovací řetězec uložit přímo do nastavení aplikace
- V Průzkumníku řešení klikněte dvakrát klikněte na ikonu Moje projektu (Visual Basic) nebo ikonu vlastnosti (C#) Chcete-li otevřít v Návrháři projektu.
- Vyberte kartu nastavení.
- Zadejte název připojovacího řetězce. Při přístupu k připojovací řetězec v kódu odkazovat tento název.
- Nastavte typ, který má (připojovací řetězec).
- Ponechte oboru nastavit na aplikaci.
- Zadejte připojovací řetězec do pole hodnoty, nebo klikněte na tlačítko se třemi tečkami (...) v poli hodnota otevřete dialogové okno Vlastnosti připojení k sestavení připojovacího řetězce.  

## <a name="editing-connection-strings-stored-in-application-settings"></a>Úpravy připojovací řetězce, které jsou uložené v nastavení aplikace
Můžete upravit informace o připojení, který je uložený v nastavení aplikace pomocí Návrháře projektu.  

### <a name="to-edit-a-connection-string-stored-in-application-settings"></a>Chcete-li upravit připojovací řetězec uložený v nastavení aplikace
- V Průzkumníku řešení klikněte dvakrát klikněte na ikonu Moje projektu (Visual Basic) nebo ikonu vlastnosti (C#) Chcete-li otevřít v Návrháři projektu.
- Vyberte kartu nastavení.
- Vyhledejte připojení, které chcete upravit a vyberte text v poli hodnota.
- Upravit připojovací řetězec v poli hodnota, nebo klikněte na tlačítko se třemi tečkami (...) v poli hodnota upravit připojení s dialogové okno Vlastnosti připojení.  

## <a name="editing-connection-strings-for-datasets"></a>Úpravy připojovací řetězce pro datové sady
Můžete upravit informace o připojení pro každý TableAdapter v datové sadě.  

### <a name="to-edit-a-connection-string-for-a-tableadapter-in-a-dataset"></a>Chcete-li upravit připojovací řetězec pro TableAdapter v datové sadě
- V Průzkumníku řešení klikněte dvakrát na datové sady (.xsd soubor), který má připojení, které chcete upravit.
- Vyberte TableAdapter nebo dotaz, který má připojení, které chcete upravit.
- V okně vlastností rozbalte uzel připojení.
- Pokud chcete rychle upravit připojovací řetězec, upravte vlastnost ConnectionString nebo klikněte na šipku dolů na vlastnost připojení a zvolit nové připojení.

## <a name="security"></a>Zabezpečení
Ukládání citlivých informací (například heslo) v připojovacím řetězci může ovlivnit zabezpečení vaší aplikace. Pomocí integrované zabezpečení systému Windows je bezpečnější způsob, jak řídit přístup k databázi.
Další informace najdete v tématu [chrání informace o připojení](/dotnet/framework/data/adonet/protecting-connection-information).
  
## <a name="see-also"></a>Viz také
[Přidání připojení](../data-tools/add-new-connections.md)