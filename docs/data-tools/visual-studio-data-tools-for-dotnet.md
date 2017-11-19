---
title: "Data nástroje sady Visual Studio pro rozhraní .NET | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3175080-1dfb-4ab8-a460-92dadbb844b4
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 6b48b16d33c62c2d0ca96eb1d55ce22682458029
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="visual-studio-data-tools-for-net"></a>Data nástroje sady Visual Studio pro .NET
Visual Studio a rozhraní .NET Framework společně poskytují rozsáhlejší rozhraní API a podpora nástrojů pro připojení k databázím, modelování data v paměti a zobrazení dat v uživatelském rozhraní. Třídy rozhraní .NET Framework, které poskytují přístup k datům funkce se označují jako [ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx). ADO.NET, spolu s daty nástrojů v sadě Visual Studio, byla původně vytvořena především pro podporu relačních databází a XML. V současnosti mnoho dodavatelů databáze NoSQL či třetích stran, nabízejí poskytovatelé ADO.NET.  
  
[.NET core](https://www.dotnetfoundation.org/netcore) podporuje ADO.NET, s výjimkou datových sad a souvisejících typů. Pokud jsou cílení na .NET Core a vyžadují vrstvu relační objekt mapování (ORM), použijte [Entity Framework Core](https://docs.microsoft.com/ef/core/).  
  
Následující diagram ukazuje zjednodušený přehled základní architektury:  
  
![Architektura technologie ADO.NET](../data-tools/media/raddata-ado-net-architecture-diagram.png "raddata Diagram architektury ADO.NET")  
  
Obvyklý pracovní postup je následující:  
  
1.  Nainstalujte vývojové nebo testovací databáze na místním počítači. V tématu [instalace databáze systémy, nástroje a ukázky](../data-tools/installing-database-systems-tools-and-samples.md). Pokud používáte služby Azure data, není nutné tento krok.  
  
2.  Test připojení k databázi (nebo služby nebo místního souboru) v sadě Visual Studio. V tématu [přidat nová připojení](../data-tools/add-new-connections.md).  
  
3.  (Volitelné) Pomocí nástrojů pro vygenerování a konfigurovat nový model. Modely založena na Entity Framework jsou doporučení výchozí pro nové aplikace. Model, kteréhokoli z nich chcete použít, je zdroj dat, který komunikuje aplikace. Model je logicky mezi databází nebo služby a aplikace.  V tématu [přidat nové zdroje dat](../data-tools/add-new-data-sources.md).  
  
4.  Přetáhněte zdroj dat z **zdroje dat** okna do Windows Forms, ASP.NET nebo Windows Presentation Foundation návrhová plocha ke generování kódu vazby dat, který se zobrazí data uživateli způsobem, který určíte. V tématu [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md).  
  
5.  Přidáte vlastní kód pro věci, jako je obchodní pravidla, vyhledávání a ověřování dat nebo využít vlastních funkcí, které zpřístupňuje základní databáze.  
  
Můžete přeskočit krok 3 a aplikaci .NET vydat příkazy přímo do databáze, místo použití modelu. V takovém případě najdete v příslušné dokumentaci od zde: [ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx). Upozorňujeme, že jste stále můžete použít Průvodce konfigurací zdroje dat a návrhářů, pro generování kódu vazby dat při naplňování vlastní objekty v paměti a poté vytvořit datovou vazbu ovládacích prvků uživatelského rozhraní k těmto objektům.
  
## <a name="see-also"></a>Viz také
[Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)