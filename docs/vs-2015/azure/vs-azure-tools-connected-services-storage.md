---
title: Přidání služby Azure Storage pomocí připojených služeb
description: Přidání služby Azure Storage do vaší aplikace pomocí dialogu Visual Studio přidání připojené služby
author: ghogen
manager: jillfra
assetId: 521ec044-ad4b-4828-8864-01decde2e758
ms.prod: visual-studio-dev14
ms.technology: vs-azure
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/26/2017
ms.author: ghogen
ms.openlocfilehash: e68f7503ecc75c03e9f4beda2003415d3175ee7e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963846"
---
# <a name="adding-azure-storage-by-using-visual-studio-connected-services"></a>Přidání služby Azure storage pomocí připojených služeb sady Visual Studio
Pomocí sady Visual Studio, můžete připojit cokoli z následujícího do služby Azure Storage s použitím **přidání připojené služby** dialogové okno:

- Cloudovou službu C#
- Mobilní služby back-end .NET
- Webové stránky ASP.NET nebo služby
- Služba ASP.NET Core
- Služba Azure WebJob

Funkce připojené služby do vašeho projektu přidá potřebné odkazy a připojovací kód a odpovídajícím způsobem upraví konfigurační soubory.

Po dokončení **přidání připojené služby** dialogové okno automaticky zobrazí dokumentaci s podrobným rozpisem kroků nutné začít pracovat s úložištěm objektů blob, fronty a tabulky.

## <a name="connect-to-azure-storage-using-the-connected-services-dialog"></a>Připojení k Azure Storage pomocí dialogového okna připojené služby
1. Otevřete projekt v sadě Visual Studio

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **připojené služby** uzel a v místní nabídce a vyberte **přidat připojenou službu**.

    ![Přidat Azure připojené služby](./media/vs-azure-tools-connected-services-storage/IC796702.png)

1. V **připojené služby** stránce **cloudové úložiště se službou Azure Storage**.

    ![Přidání služby Azure Storage](./media/vs-azure-tools-connected-services-storage/add-azure-storage.png)

1. V **služby Azure Storage** dialogového okna, vyberte existující účet úložiště a vyberte **přidat**.

    Pokud potřebujete vytvořit účet úložiště, přejděte k dalšímu kroku. V opačném případě přejděte ke kroku 6.

    ![Přidat existující účet úložiště do projektu](./media/vs-azure-tools-connected-services-storage/select-azure-storage-account.png)

1. Chcete-li vytvořit účet úložiště:

   1. Vyberte **vytvořit nový účet úložiště** v dolní části dialogového okna.

   1. Vyplňte **vytvořit účet úložiště** dialogového okna a vyberte **vytvořit**.

       ![Nový účet úložiště Azure](./media/vs-azure-tools-connected-services-storage/create-storage-account.png)

   1. Když **služby Azure Storage** se zobrazí dialogové okno, v seznamu se zobrazí nový účet úložiště. V seznamu vyberte nový účet úložiště a vyberte **přidat**.

1. Úložiště připojené služby se zobrazí v části **odkazy na služby** uzlu projektu.

## <a name="how-your-project-is-modified"></a>Jak se váš projekt změnil
Po dokončení dialogové okno sady Visual Studio přidá odkazy a změní některé konfigurační soubory. Konkrétní změny závisí na typu projektu:

- Projekt ASP.NET – [co se stalo – projekty ASP.NET](http://go.microsoft.com/fwlink/p/?LinkId=513126)
- Projekt ASP.NET Core – [co se stalo – projekty ASP.NET 5](http://go.microsoft.com/fwlink/p/?LinkId=513124)
- Projekt cloudové služby (webové role a role pracovního procesu) - [co se stalo – projekty cloudových služeb](http://go.microsoft.com/fwlink/p/?LinkId=516965)
- Projektu úlohy WebJob - [co se stalo – projekty webové úlohy](/azure/visual-studio/vs-storage-webjobs-what-happened)

## <a name="next-steps"></a>Další kroky
- [Fórum na webu MSDN: Azure Storage](https://social.msdn.microsoft.com/forums/azure/home?forum=windowsazuredata)
- [Blog týmu Microsoft Azure Storage](http://blogs.msdn.com/b/windowsazurestorage/)
- [Dokumentace ke službě Azure Storage](https://docs.microsoft.com/azure/storage/)
