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
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: da8555d4246d2177b3d97eeef8d24c7b4a22b31d
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925639"
---
# <a name="how-to-add-update-or-remove-a-wcf-data-service-reference"></a>Postupy: Přidání, aktualizace nebo odebrání odkazu na službu WCF Data Service
*Odkaz na službu* umožňuje projektu přístup k jednomu nebo více [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)]. Pomocí dialogového okna **Přidat odkaz na službu** můžete vyhledat [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] v aktuálním řešení, místně, v místní síti nebo na internetu.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="add-a-service-reference"></a>Přidat odkaz na službu

### <a name="to-add-a-reference-to-an-external-service"></a>Přidání odkazu na externí službu

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na název projektu, do kterého chcete přidat službu, a pak klikněte na **Přidat odkaz na službu**.

     Zobrazí se dialogové okno **Přidat odkaz na službu** .

2. Do pole **adresa** zadejte adresu URL služby a potom kliknutím na tlačítko **Přejít** vyhledejte službu. Pokud služba implementuje zabezpečení uživatelského jména a hesla, může se zobrazit výzva k zadání uživatelského jména a hesla.

    > [!NOTE]
    > Měli byste odkazovat jenom na služby z důvěryhodného zdroje. Přidání odkazů z nedůvěryhodného zdroje může ohrozit zabezpečení.

     Můžete také vybrat adresu URL ze seznamu **adres** , ve kterém jsou uloženy předchozí 15 adres URL, na kterých byla nalezena platná metadata služby.

     Po provedení hledání se zobrazí indikátor průběhu. Hledání můžete kdykoli zastavit kliknutím na tlačítko **zastavit**.

3. V seznamu **služby** rozbalte uzel pro službu, kterou chcete použít, a vyberte sadu entit.

4. Do pole **obor názvů** zadejte obor názvů, který chcete použít pro referenci.

5. Kliknutím na tlačítko **OK** přidejte odkaz na projekt.

     Je vygenerován klient služby (proxy) a do souboru *App. config* je přidána metadata, která popisují službu.

### <a name="to-add-a-reference-to-a-service-in-the-current-solution"></a>Přidání odkazu na službu v aktuálním řešení

1. V **Průzkumník řešení**klikněte pravým tlačítkem myši na název projektu, do kterého chcete přidat službu, a pak klikněte na **Přidat odkaz na službu**.

    Zobrazí se dialogové okno **Přidat odkaz na službu** .

2. Klikněte na tlačítko **zjistit**.

    Do seznamu **služeb** se [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] přidají všechny služby (a služby WCF) v aktuálním řešení.

3. V seznamu **služby** rozbalte uzel pro službu, kterou chcete použít, a vyberte sadu entit.

4. Do pole **obor názvů** zadejte obor názvů, který chcete použít pro referenci.

5. Kliknutím na tlačítko **OK** přidejte odkaz na projekt.

    Klient služby (proxy) vygeneruje a metadata, která popisují službu, se přidají do souboru *App. config* .

## <a name="update-a-service-reference"></a>Aktualizovat odkaz na službu
Model EDM (Entity Data Model) [!INCLUDE[ssAstoria](../data-tools/includes/ssastoria_md.md)] se někdy změní. Pokud k tomu dojde, musíte aktualizovat odkaz na službu.

### <a name="to-update-a-service-reference"></a>Aktualizace odkazu na službu

- V **Průzkumník řešení**klikněte pravým tlačítkem na odkaz na službu a pak klikněte na **aktualizovat odkaz na službu**.

     Dialogové okno průběh se zobrazí, když je odkaz aktualizován z jeho původního umístění a klient služby se znovu vygeneruje, aby odrážel všechny změny v metadatech.

## <a name="remove-a-service-reference"></a>Odebrat odkaz na službu
Pokud se už odkaz na službu nepoužívá, můžete ho odebrat z řešení.

### <a name="to-remove-a-service-reference"></a>Odebrání odkazu na službu

- V **Průzkumník řešení**klikněte pravým tlačítkem na odkaz na službu a pak klikněte na **Odstranit**.

     Klient služby se odebere z řešení a metadata, která popisují službu, se odeberou ze souboru *App. config* .

    > [!NOTE]
    > Jakýkoli kód, který odkazuje na odkaz na službu, je nutné odebrat ručně.

## <a name="see-also"></a>Viz také:

- [Služby Windows Communication Foundation Services a WCF Data Services v aplikaci Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)