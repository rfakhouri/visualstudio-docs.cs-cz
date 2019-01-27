---
title: Sada nástrojů, karta Data
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- Toolbox, Data tab
- Data tab, Toolbox
- data [Visual Studio], Toolbox
ms.assetid: 2ae38b2a-29d2-461c-a67d-29dad274bf45
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0f30bc874f5ed3debecf24a3259a8b13c9c38d49
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54997400"
---
# <a name="toolbox-data-tab"></a>Sada nástrojů, karta Data

Zobrazí data objekty, které můžete přidat do formuláře a komponenty. **Data** karty **nástrojů** se zobrazí, když vytvoříte projekt, který má přidružený designer. **Nástrojů** se zobrazí ve výchozím nastavení v integrovaném vývojovém prostředí sady Visual Studio; Pokud chcete zobrazit **nástrojů**vyberte **nástrojů** z **Zobrazení** nabídky.

> [!TIP]
> Spuštění Průvodce konfigurací zdroje dat automaticky vytvoří a nakonfiguruje většina datových položek. Další informace najdete v tématu [přidat nové zdroje dat](../../data-tools/add-new-data-sources.md).

## <a name="ui-element-list"></a>Seznam prvků uživatelského rozhraní

Chcete-li přejít přímo na stránce dokumentace rozhraní .NET Framework pro komponentu, stiskněte **F1** na položku v **nástrojů** nebo na položku součásti na hlavním panelu v návrháři.

|Název|Popis|
|----------|-----------------|
|<xref:System.Data.DataSet>|Přidá instanci typovou nebo netypovou datovou sadu do formuláře nebo komponenty. Při přetažení tohoto objektu na Návrhář zobrazí dialogové okno, které vám umožní vybrat existující třídy typové datové sady nebo určit, že chcete vytvořit novou, prázdnou, netypové datové sady. **Poznámka:**  Je velmi riskantní používat <xref:System.Data.DataSet> objektu na **nástrojů** k vytvoření nové schéma typové datové sady a třídy. Další informace najdete v tématu [vytvoření a konfigurace datové sady](../../data-tools/create-and-configure-datasets-in-visual-studio.md).|
|<xref:System.Windows.Forms.DataGridView>|Poskytuje výkonný a flexibilní způsob, jak zobrazit data ve formátu tabulky.|
|<xref:System.Windows.Forms.BindingSource>|Zjednodušuje proces vytvoření vazby ovládacích prvků do podkladového zdroje dat.|
|<xref:System.Windows.Forms.BindingNavigator>|Představuje navigaci a manipulaci s uživatelského rozhraní (UI) pro ovládací prvky ve formuláři, které jsou vázány na data.|

## <a name="see-also"></a>Viz také

- [Přístup k datům v sadě Visual Studio](../../data-tools/accessing-data-in-visual-studio.md)
- [Visual Studio Data Tools for .NET](../../data-tools/visual-studio-data-tools-for-dotnet.md)
- [Nástroje datových sad v sadě Visual Studio](../../data-tools/dataset-tools-in-visual-studio.md)
- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../../data-tools/bind-controls-to-data-in-visual-studio.md)
- [Vytvoření vazby ovládacích prvků modelu Windows Forms k datům v sadě Visual Studio](../../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
- [Úprava dat v datových sadách](../../data-tools/edit-data-in-datasets.md)
- [Ověřování dat v datových sadách](../../data-tools/validate-data-in-datasets.md)