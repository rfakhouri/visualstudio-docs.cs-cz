---
title: 'Postupy: Přidání, aktualizace nebo odebrání odkazu na službu WCF Data Service'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- service references [Visual Studio]
- WCF Data Service reference
- WCF data service references
- ADO.NET service references
- ADO.NET Data Service reference
ms.assetid: 892ebf37-3af4-472e-8744-92837677d611
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 9e39b28a3de5aa97ac7c0673cd16b71508ae4276
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31925973"
---
# <a name="how-to-add-update-or-remove-a-wcf-data-service-reference"></a>Postupy: Přidání, aktualizace nebo odebrání odkazu na službu WCF Data Service
A *odkaz na službu* umožňuje projektu přístup k jedné nebo více [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]. Použití **přidat odkaz na službu** dialogové okno pro vyhledávání [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] v aktuálním řešení, místně, v místní síti nebo na Internetu.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="adding-a-service-reference"></a>Přidání odkazu na službu

#### <a name="to-add-a-reference-to-an-external-service"></a>Chcete-li přidat odkaz na externí služby

1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt, který chcete přidat službu a pak klikněte na tlačítko **přidat odkaz na službu**.

     **Přidat odkaz na službu** zobrazí se dialogové okno.

2.  V **adresu** pole, zadejte adresu URL pro službu a pak klikněte na tlačítko **přejděte** pro vyhledávání pro službu. Pokud služba implementuje zabezpečení uživatelské jméno a heslo, budete vyzváni k zadání uživatelského jména a hesla.

    > [!NOTE]
    >  Služby by měl odkazovat jenom z důvěryhodného zdroje. Přidání odkazů z nedůvěryhodných zdrojů může ohrozit zabezpečení.

     Můžete také vybrat adresu URL z **adresu** seznam, který ukládá předchozí 15 adres URL, na kterých metadata platný služby nebyla nalezena.

     Indikátor průběhu se zobrazí, když se provádí vyhledávání. Hledání kdykoli můžete ukončit kliknutím na **Zastavit**.

3.  V **služby** seznamu, rozbalte uzel pro službu, kterou chcete použít a vyberte sadu entit.

4.  V **Namespace** zadejte obor názvů, který chcete použít pro odkaz.

5.  Klikněte na tlačítko **OK** se přidat odkaz na projekt.

     Klient služby (proxy) je generován a metadata, která popisuje služby se přidá do souboru app.config.

#### <a name="to-add-a-reference-to-a-service-in-the-current-solution"></a>Chcete-li přidat odkaz na službu v aktuálním řešení

1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt, který chcete přidat službu a pak klikněte na tlačítko **přidat odkaz na službu**.

     **Přidat odkaz na službu** zobrazí se dialogové okno.

2.  Klikněte na tlačítko **zjistit**.

     Všechny služby (obě [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] a služby WCF) v aktuálním řešení, které jsou přidány do **služby** seznamu.

3.  V **služby** seznamu, rozbalte uzel pro službu, kterou chcete použít a vyberte sadu entit.

4.  V **Namespace** zadejte obor názvů, který chcete použít pro odkaz.

5.  Klikněte na tlačítko **OK** se přidat odkaz na projekt.

     Klient služby (proxy) je generován a metadata, která popisuje služby se přidá do souboru app.config.

## <a name="updating-a-service-reference"></a>Aktualizace odkazu na službu
 Datový Model Entity pro [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] někdy změní. Pokud k tomu dojde, je třeba aktualizovat odkaz na službu.

#### <a name="to-update-a-service-reference"></a>K aktualizaci odkazu na službu

-   V **Průzkumníku řešení**, klikněte pravým tlačítkem na odkaz na službu a pak klikněte na tlačítko **aktualizovat odkaz na službu**.

     Zatímco odkaz je aktualizována z původního umístění, a klient služby je vygenerován tak, aby odrážela všechny změny v metadatech, zobrazí se dialogové okno průběhu.

## <a name="removing-a-service-reference"></a>Odebrání odkazu na službu
 Pokud se už používá odkazu na službu, můžete jej odebrat z vašeho řešení.

#### <a name="to-remove-a-service-reference"></a>Chcete-li odebrat odkaz na službu

-   V **Průzkumníku řešení**, klikněte pravým tlačítkem na odkaz na službu a pak klikněte na tlačítko **odstranit**.

     Klienta služby se odebere z řešení a metadata, která popisuje službu se odeberou ze souboru app.config.

    > [!NOTE]
    >  Kód, který odkazuje na odkaz na službu bude muset ručně odstranit.

## <a name="see-also"></a>Viz také

- [Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)