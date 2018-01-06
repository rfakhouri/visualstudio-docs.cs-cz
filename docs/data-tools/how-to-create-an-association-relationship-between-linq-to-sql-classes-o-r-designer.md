---
title: "Jak vytvořit relaci mezi třídy LINQ to SQL pomocí Návrhář relací objektů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56133e65-81f3-44c3-bc28-ffdd0671a0d2
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 5c86eff5c25dbabb368d7d90ed46be718b8db8e7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-an-association-between-linq-to-sql-classes-or-designer"></a>Postupy: vytvoření přidružení mezi technologie LINQ to SQL třídy (Návrhář relací objektů)
Přidružení mezi třídami entity v [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] se podobá se relace mezi tabulkami v databázi. Můžete vytvořit přidružení mezi tříd entit s použitím **přidružení Editor** dialogové okno.  
  
Při použití musíte vybrat nadřazenou třídu a podřízené třídy **přidružení Editor** dialogové okno vytvořit přidružení. Nadřazené třídy je třída entity, která obsahuje primární klíč. Třída podřízené je třídu entity, která obsahuje cizí klíč. Například pokud entity třídy byly vytvořeny, které jsou namapovány na tabulky zákazníků Northwind a objednávky, třídu Customer by nadřazené třídy a třídy pořadí by podřízené třídy.  
  
> [!NOTE]
>  Při přetažení tabulky z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]), se automaticky vytvoří podle existující přidružení cizí klíč relace v databázi.  

## <a name="association-properties"></a>Vlastnosti přidružení
Po vytvoření přidružení, když vyberete přidružení v Návrháři relací objektů, jsou některé konfigurovatelné vlastnosti v **vlastnosti** okno. (Přidružení je řádek mezi související třídy.) Následující tabulka obsahuje popis vlastností přidružení.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|**Mohutnost**|Určuje, zda je přidružení na více nebo 1: 1.|  
|**Podřízená – vlastnost**|Určuje, zda chcete vytvořit vlastnost na nadřazeného objektu, který je kolekce nebo odkaz na podřízené záznamy na straně přidružení cizího klíče. Například v přidružení mezi zákazníkem a pořadí Pokud **vlastnost podřízeného** je nastaven na **True**, vlastnost s názvem objednávky je vytvořen v nadřazené třídy.|  
|**Nadřazený klíč**|Vlastnost na podřízené třídu, která odkazuje na související nadřazené třídy. Například v přidružení mezi zákazníkem a pořadí, je vlastnost s názvem zákazníkovi, který odkazuje na související odběratele pro pořadí vytvořili na třídě pořadí.|  
|**Zúčastněných vlastnosti**|Zobrazí vlastnosti přidružení a poskytuje **třemi tečkami** tlačítko (...), které se znovu otevře **přidružení Editor** dialogové okno.|  
|**Jedinečné**|Určuje, jestli cizí cílových sloupců mají omezení jedinečnosti.|  
  
## <a name="to-create-an-association-between-entity-classes"></a>K vytvoření přidružení mezi třídami entity
  
1.  Klikněte pravým tlačítkem na třídu entity, která představuje nadřazené třídy v association, přejděte na **přidat**a potom klikněte na **přidružení**.  
  
2.  Ověřte, že správný **nadřazené třídy** je vybraný v **přidružení Editor** dialogové okno.  
  
3.  Vyberte **podřízené třídy** do pole se seznamem.  
  
4.  Vyberte **vlastnosti přidružení** které se týkají třídy. Obvykle to mapuje relace cizího klíče, které jsou definované v databázi. Například v přidružení zákazníci a objednávky **vlastnosti přidružení** jsou CustomerID pro každou třídu.  
  
5.  Klikněte na tlačítko **OK** vytváření přidružení.  
  
## <a name="see-also"></a>Viz také
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
[Návod: Vytváření třídy LINQ to SQL](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
[Technologie LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)   
[Metody DataContext (Návrhář relací objektů)](../data-tools/datacontext-methods-o-r-designer.md)   
[Postupy: Znázornění primárních klíčů](/dotnet/framework/data/adonet/sql/linq/how-to-represent-primary-keys)