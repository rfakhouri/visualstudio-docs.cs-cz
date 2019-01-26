---
title: 'Postupy: Ukládání dat pomocí transakce'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- saving data, using transactions
- System.Transactions namespace
- transactions, saving data
- data [Visual Studio], saving
ms.assetid: 8b835e8f-34a3-413d-9bb5-ebaeb87f1198
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: ecf63cc03af13cadb5791e2f0f5a058feedb8418
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54934072"
---
# <a name="how-to-save-data-by-using-a-transaction"></a>Postupy: Ukládání dat pomocí transakce

Ukládání dat v transakci pomocí <xref:System.Transactions> oboru názvů. Použití <xref:System.Transactions.TransactionScope> objektu k účasti v transakci, která se automaticky spravuje za vás.

Projekty nejsou vytvořeny s odkazem na *System.Transactions* sestavení, takže je třeba ručně přidat odkaz na projektech, které používají transakce.

Nejjednodušší způsob, jak implementovat transakce je k vytvoření instance <xref:System.Transactions.TransactionScope> objekt `using` příkazu. (Další informace najdete v tématu [příkaz Using](/dotnet/visual-basic/language-reference/statements/using-statement), a [příkaz Using](/dotnet/csharp/language-reference/keywords/using-statement).) Kód, který běží v rámci `using` příkaz účastní v transakci.

Chcete-li zapsat transakci, zavolejte <xref:System.Transactions.TransactionScope.Complete%2A> metody jako poslední příkaz v pomocí blokovat.

Chcete-li vrátit zpět transakci, vyvolat výjimku před voláním <xref:System.Transactions.TransactionScope.Complete%2A> metody.

## <a name="to-add-a-reference-to-the-systemtransactionsdll"></a>Chcete-li přidat odkaz na System.Transactions.dll

1.  Na **projektu** nabídce vyberte možnost **přidat odkaz**.

2.  Na **.NET** kartu (**systému SQL Server** kartu pro projekty na SQL serveru) vyberte **System.Transactions**a pak vyberte **OK**.

     Odkaz na *System.Transactions.dll* se přidá do projektu.

## <a name="to-save-data-in-a-transaction"></a>Chcete-li uložit data v transakci

-   Přidejte kód pro uložení dat v rámci nástroje pomocí příkazu, který obsahuje transakci. Následující kód ukazuje, jak vytvořit a vytvoření instance <xref:System.Transactions.TransactionScope> objektu v pomocí příkazu:

     [!code-vb[VbRaddataSaving#11](../data-tools/codesnippet/VisualBasic/save-data-by-using-a-transaction_1.vb)]
     [!code-csharp[VbRaddataSaving#11](../data-tools/codesnippet/CSharp/save-data-by-using-a-transaction_1.cs)]

## <a name="see-also"></a>Viz také:

- [Ukládání dat zpět do databáze](../data-tools/save-data-back-to-the-database.md)
- [Návod: Ukládání dat do transakce](../data-tools/save-data-in-a-transaction.md)