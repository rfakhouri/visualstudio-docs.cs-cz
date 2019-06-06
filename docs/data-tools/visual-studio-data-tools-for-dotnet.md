---
title: Datové nástroje pro .NET
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3175080-1dfb-4ab8-a460-92dadbb844b4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
- dotnet
ms.openlocfilehash: a4a62f629244d44680b3d5ac3233bd45b975302e
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2019
ms.locfileid: "66745309"
---
# <a name="visual-studio-data-tools-for-net"></a>Visual Studio Data Tools for .NET

Visual Studio a .NET společně poskytují rozsáhlé rozhraní API a podpora nástrojů pro připojení k databázím, modelování dat v paměti a zobrazení dat v uživatelském rozhraní. Třídy rozhraní .NET, které poskytují přístup k datům funkce jsou označovány jako [ADO.NET](/dotnet/framework/data/adonet/index). ADO.NET, spolu s daty nástroje v sadě Visual Studio, je navržená především pro podporu relačních databází a XML. V dnešních dnech mnoho dodavatelů databáze typu NoSQL nebo třetími stranami, nabízejí poskytovatele ADO.NET.

[.NET core](/dotnet/core/) podporuje technologie ADO.NET, s výjimkou datových sad a jejich souvisejících typů. Pokud cílíte .NET Core a vyžadují vrstvu objektově relační mapování (ORM), použijte [Entity Framework Core](/ef/core/).

Následující diagram znázorňuje zjednodušenou zobrazení základní architektury:

![Architektura ADO.NET](../data-tools/media/raddata-ado-net-architecture-diagram.png)

## <a name="typical-workflow"></a>Typický pracovní postup

Typický pracovní postup je následující:

1. Nainstalujte vývojové nebo testovací databáze na místním počítači. Zobrazit [instalace systémů databází, nástroje a ukázky](../data-tools/installing-database-systems-tools-and-samples.md). Pokud používáte službu Azure data, tento krok není nezbytný.

2. Otestujte připojení k databázi (nebo službu nebo místní soubor) v sadě Visual Studio. Zobrazit [přidat nové připojení](../data-tools/add-new-connections.md).

3. (Volitelné) Pomocí nástrojů vygenerovat a nakonfigurovat nový model. Modely založené na rozhraní Entity Framework jsou výchozí doporučení pro nové aplikace. Model, kteréhokoli z nich použijete, je zdroj dat, pomocí kterého aplikace komunikuje. Model je logicky mezi databází nebo služby a aplikace. Zobrazit [přidat nové zdroje dat](../data-tools/add-new-data-sources.md).

4. Přetáhnout zdroje dat z **zdroje dat** okno na návrhovou plochu Windows Forms, ASP.NET nebo Windows Presentation Foundation ke generování kódu vázání dat, která tato data budou zobrazovat uživateli způsobem, který zadáte. Zobrazit [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md).

5. Přidání vlastního kódu pro takové věci, jako jsou obchodní pravidla, vyhledávání a ověřování dat nebo využívat vlastní funkce, které zpřístupňuje základní databáze.

Můžete přeskočit krok 3 a programu .NET aplikace vydat příkazy přímo do databáze, nikoli pomocí modelu. V takovém případě najdete příslušnou dokumentaci: [ADO.NET](/dotnet/framework/data/adonet/index). Všimněte si, že se můžete stále použít **Průvodce konfigurací zdroje dat** , návrháři, generovat datové vazby kód při naplňování vlastních objektů v paměti a potom vytvořte datovou vazbu ovládacích prvků uživatelského rozhraní na tyto objekty.

## <a name="see-also"></a>Viz také:

- [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)