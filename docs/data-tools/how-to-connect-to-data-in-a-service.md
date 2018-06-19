---
title: 'Postupy: Připojování k datům ve službě'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- data [Visual Studio], connecting to Web services
- data sources, creating from Web services
- data [Visual Studio], reading from Web services
- reading data, from Web services
- Web services, reading data
- Web services, as data sources
- Web services, connecting
ms.assetid: a6b54353-05fe-4e5c-8631-90231fc95504
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 3975d7f0bcfc9b80c944c892cde52f2b625e0bbf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31921098"
---
# <a name="how-to-connect-to-data-in-a-service"></a>Postupy: Připojování k datům ve službě

Připojení aplikace s daty vrácenými ze služby spuštěním [Průvodce konfigurací zdroje dat](../data-tools/media/data-source-configuration-wizard.png) a výběrem **služby** na **zvolte typ zdroje dat**stránky.

Po dokončení průvodce, odkaz na službu se přidá do projektu a je okamžitě k dispozici v [okno zdroje dat](add-new-data-sources.md).

> [!NOTE]
> Položky, které se zobrazují v **zdroje dat** okna jsou závislé na informace, které se vrátí službu. Některé služby nemusí poskytuje dostatek informací **Průvodce konfigurací zdroje dat** vytvořit vazbu objekty. Například pokud služba vrátí netypové datové sady, pak se neobjeví žádné položky v **okno zdroje dat** po dokončení průvodce. To je proto netypové datové sady neposkytují schématu, proto Průvodce nemá dostatek informací pro vytvoření zdroje dat.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="to-connect-your-application-to-a-service"></a>Chcete-li aplikaci připojit ke službě

1.  Na **Data** nabídky, klikněte na tlačítko **přidat nový zdroj dat**.

2.  Vyberte **služby** na **zvolte typ zdroje dat** a pak klikněte na tlačítko **Další**.

3.  Zadejte adresu služby, kterou chcete použít, nebo klikněte na tlačítko **Discover** vyhledání služeb v aktuálním řešení a potom klikněte na **přejděte**.

4.  Volitelně můžete nový **Namespace** lze zadat místo výchozí hodnota.

    > [!NOTE]
    > Klikněte na tlačítko **Upřesnit** otevřete [konfigurace služby odkaz dialogové okno](../data-tools/configure-service-reference-dialog-box.md).

5.  Klikněte na tlačítko **OK** přidat odkaz na službu do projektu.

6.  Klikněte na tlačítko **Dokončit**.

     Zdroj dat je přidaný do **zdroje dat** okno.

## <a name="next-steps"></a>Další kroky

K přidání funkcí do vaší aplikace, vyberte položku v **zdroje dat** okna a přetáhněte ji na formulář pro vytvoření vázané ovládací prvky. Další informace najdete v tématu [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md).

## <a name="see-also"></a>Viz také

- [Vytvoření vazby ovládacích prvků WPF k datové službě WCF](../data-tools/bind-wpf-controls-to-a-wcf-data-service.md)
- [Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)