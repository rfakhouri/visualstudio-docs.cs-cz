---
title: Přehled vícevrstvých datových aplikací
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- presentation tier
- middle tier
- data tier
- n-tier applications, about n-tier applications
ms.assetid: 1020581d-eaaa-41a2-aca4-bf4c212895f6
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 4e386c052b43ee62ddde0516fa203298fe1babe5
ms.sourcegitcommit: e9d1018a01af62c3dc5aeb6b325faba7e20bd496
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/28/2018
ms.locfileid: "37089027"
---
# <a name="n-tier-data-applications-overview"></a>Přehled vícevrstvých datových aplikací
*N-vrstvá* data aplikací jsou data aplikací, které jsou rozdělené do několika *vrstev*. Nazývají se také „distribuované aplikace“ a „vícevrstvé aplikace“. N-vrstvé aplikace oddělují zpracování do samostatných vrstev, které jsou distribuovány mezi klientem a serverem. Při vývoji aplikací s přístupem k datům by mělo být cíleno na rozdělení mezi různými úrovněmi, které aplikaci tvoří.

Typická n-vrstvá aplikace obsahuje prezentační vrstvu, střední vrstvu a datovou vrstvu. Nejjednodušším způsobem rozdělení různých vrstev v n-vrstvé aplikaci je vytvoření samostatných projektů pro každou úroveň, kterou chcete do aplikace zahrnout. Prezentační vrstvou může být například Formulářová aplikace Windows. Naproti tomu logikou přístupu k datům může být knihovna tříd, která je umístěna ve střední vrstvě. Prezentační vrstva může navíc komunikovat s logikou přístupu dat ve střední vrstvě prostřednictvím služby. Rozdělení komponent aplikace do oddělených vrstev zvyšuje udržovatelnost a škálovatelnost aplikace. Je to dáno tím, že je umožněno snadnější přijímání nových technologií, které mohou být použity v jedné vrstvě, aniž by bylo nutné změnit návrh celého řešení. Kromě toho n-vrstvá aplikace obvykle ukládá citlivé informace do střední vrstvy, což zajišťuje izolaci od prezentační vrstvy.

Aplikace Visual Studio obsahuje několik funkcí, které usnadní vývojářům vytvářet n-vrstvé aplikace:

-   Poskytuje datovou sadu **DataSet projekt** vlastnost, která umožňuje oddělit datovou sadu (data entity layer) a TableAdapters (data access layer) do diskrétní projektů.

-   [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md) poskytuje nastavení k vytvoření třídy kontextu DataContext a data do samostatné obory názvů. Tato skutečnost umožňuje logické rozdělení přístupu k datům a vrstev datové entity.

-   [Technologie LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) poskytuje <xref:System.Data.Linq.Table%601.Attach%2A> metoda, která umožňuje shromažďování DataContext z různých vrstev v aplikaci. Další informace najdete v tématu [N-vrstvá a vzdálené aplikace s dotazy LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql).

## <a name="presentation-tier"></a>Prezentační vrstva
*Prezentační vrstvy* je vrstvy, ve kterém uživatelé pracují s aplikací. Často také obsahuje další aplikační logiku. Mezi typické komponenty prezentační vrstvy patří:

-   Komponenty datové vazby, jako je například <xref:System.Windows.Forms.BindingSource> a <xref:System.Windows.Forms.BindingNavigator>.

-   Objekt reprezentace dat, jako například [technologie LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) tříd entit pro použití v prezentační vrstvě.

Prezentační vrstva obvykle přistoupí střední vrstvy pomocí odkazu na službu (například [služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) aplikace). Prezentační vrstva obvykle nepřistupuje přímo k datové vrstvě. Prezentační vrstva komunikuje s datovou vrstvou prostřednictvím součásti datového přístupu v rámci střední vrstvy.

## <a name="middle-tier"></a>Střední vrstva
*Střední vrstvy* je vrstva, která prezentační vrstvou a data vrstvy používat pro komunikaci mezi sebou. Mezi typické komponenty střední vrstvy patří:

-   Obchodní logika, jako jsou obchodní pravidla a ověření dat.

-   Komponenty datového přístupu a logiky, jako je například:

    -   [TableAdapters](create-and-configure-tableadapters.md) a [DataAdapters a DataReaders](/dotnet/framework/data/adonet/dataadapters-and-datareaders).

    -   Objekt reprezentace dat, jako například [technologie LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) tříd entit.

    -   Běžné služby aplikací, jako je například ověření, autorizace a přizpůsobení.

Následující obrázek znázorňuje funkce a technologie, které jsou k dispozici v aplikaci Visual Studio a které je možné v rámci n-vrstvé aplikace umístit do střední vrstvy.

![Střední vrstvy součásti](../data-tools/media/ntiermid.png) střední vrstvy

Střední vrstva se obvykle připojuje k datové vrstvě pomocí datového připojení. Datové připojení je obvykle uloženo v komponentě datového přístupu.

## <a name="data-tier"></a>Datová vrstva
*Datové vrstvy* je v podstatě serveru, která ukládá data aplikace (například serveru se systémem [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)]).

Následující obrázek znázorňuje funkce a technologie, které jsou k dispozici v aplikaci Visual Studio a které je možné v rámci n-vrstvé aplikace umístit do datové vrstvy.

![Datové vrstvy součásti](../data-tools/media/ntierdatatier.png) datové vrstvy

K datové vrstvě nelze přistupovat přímo z klienta v prezentační vrstvě. Namísto toho je ke komunikaci mezi prezentační a datovou vrstvou použita komponenta datového přístupu ve střední vrstvě.

## <a name="help-for-n-tier-development"></a>Nápověda pro vývoj n vrstvá
Následující témata obsahují informace o práci s n-vrstvými aplikacemi:

[Rozdělování datových sad a objektů TableAdapter do různých projektů](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)

[Návod: Vytvoření víceúrovňové datové aplikace](../data-tools/walkthrough-creating-an-n-tier-data-application.md)

[N-vrstvá a vzdálené aplikace s dotazy LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)

## <a name="see-also"></a>Viz také:

- [Návod: Vytvoření víceúrovňové datové aplikace](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [Hierarchická aktualizace](../data-tools/hierarchical-update.md)
- [Datové sady nástrojů v sadě Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)
- [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)