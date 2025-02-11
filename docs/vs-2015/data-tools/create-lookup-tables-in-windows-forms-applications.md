---
title: Vytváření vyhledávacích tabulek v aplikacích Windows Forms | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- lookup tables
- lookup tables, creating
ms.assetid: 0edd5385-c381-4b17-9096-74e2778db9d5
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: af9777667bef466dc97ea3a3d239f83f766816da
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65693956"
---
# <a name="create-lookup-tables-in-windows-forms-applications"></a>Vytváření vyhledávacích tabulek v aplikacích Windows Forms
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Termín *vyhledávací tabulka* popisuje ovládací prvky, které jsou vázány na dvě související tabulky dat. Tyto vyhledávací ovládací prvky zobrazují data v první tabulce na základě hodnoty vybrané v druhé tabulce.  
  
 Vyhledávací tabulky lze vytvořit přetažením hlavního uzlu nadřazené tabulky (z [okna zdroje dat](https://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)) na ovládací prvek na formuláři, který je již vázán na sloupec v související podřízené tabulky.  
  
 Předpokládejme například tabulku `Orders` v prodejní databázi. Každý záznam v `Orders` obsahuje tabulku `CustomerID`, určující, který zákazník objednávku vystavil. `CustomerID` je cizí klíč odkazující na záznam zákazníka v tabulce `Customers`. V tomto scénáři, rozbalte `Orders` v tabulku **zdroje dat** okno a nastavit hlavní uzel **podrobnosti**. Nastavte `CustomerID` sloupce <xref:System.Windows.Forms.ComboBox> (nebo jakýkoli jiný ovládací prvek, který podporuje vazbu vyhledávání) a přetáhněte ji `Orders` uzlu do formuláře. A konečně, přetáhněte `Customers` uzlu na ovládací prvek, který je vázán na odpovídající sloupec – v tomto případě <xref:System.Windows.Forms.ComboBox> vázán na `CustomerID` sloupce.  
  
## <a name="to-databind-a-lookup-control"></a>Vytvoření datové vazby ovládacího prvku vyhledávání  
  
1. Otevřít **zdroje dat** okna.  
  
    > [!NOTE]
    > Vyhledávací tabulky vyžadují dvě souvisejících tabulky nebo objekty jsou k dispozici v **zdroje dat** okna.
  
2. Rozbalte uzly v **zdroje dat** okna, dokud se nezobrazí nadřazená tabulka a všechny její sloupce a také související podřízené tabulky a všechny jejich sloupce.  
  
    > [!NOTE]
    > Uzel podřízené tabulky je uzel, který je zobrazen v podřízeném uzlu, který lze rozbalit v nadřazené tabulce.  
  
3. Změňte typ přetažení podřízené tabulky na **podrobnosti** tak, že vyberete **podrobnosti** ze seznamu ovládacího prvku na uzlu podřízené tabulky. Další informace najdete v tématu [nastavení ovládacího prvku, který má být vytvořen při přetažení z okna zdroje dat](../data-tools/set-the-control-to-be-created-when-dragging-from-the-data-sources-window.md).  
  
4. Vyhledejte uzel, který odpovídá oběma tabulkám ( `CustomerID` uzlu v předchozím příkladu). Změnit jeho typ přetažení <xref:System.Windows.Forms.ComboBox> tak, že vyberete **– pole se seznamem** ze seznamu ovládacích prvků.  
  
5. Přetáhněte hlavní uzel podřízené tabulky z **zdroje dat** okna do formuláře.  
  
     Na formuláři se zobrazí ovládací prvky s datovou vazbou (včetně popisků) a pruh nástrojů (<xref:System.Windows.Forms.BindingNavigator>). A [datovou sadu](../data-tools/dataset-tools-in-visual-studio.md), TableAdapter, <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> zobrazují v panelu komponent.  
  
6. Nyní přetáhněte hlavní uzel nadřazené tabulky z **zdroje dat** okno přímo na ovládací prvek vyhledávání ( <xref:System.Windows.Forms.ComboBox>).  
  
     Nyní jsou vytvořeny vazby vyhledávání. Specifické vlastnosti, které byly nastaveny na ovládacím prvku, naleznete v tabulce níže.  
  
    |Vlastnost|Vysvětlivky k nastavení|  
    |--------------|----------------------------|  
    |**DataSource**|Aplikace Visual Studio nastaví tuto vlastnost na zdroj <xref:System.Windows.Forms.BindingSource> vytvořený pro tabulku, která byla přetažena na ovládací prvek (na rozdíl od zdroje <xref:System.Windows.Forms.BindingSource> vytvořeného při vytvoření ovládacího prvku).<br /><br /> Pokud je nutné provést úpravu, nastavte ji na zdroj <xref:System.Windows.Forms.BindingSource> tabulky se sloupcem, který chcete zobrazit.|  
    |**DisplayMember**|Aplikace Visual Studio nastaví tuto vlastnost na první sloupec po primárním klíči, který má datový typ řetězec, u tabulky, která je přetažena na ovládací prvek.<br /><br /> Pokud je nutné provést úpravu, nastavte tuto vlastnost na název sloupce, který chcete zobrazit.|  
    |**ValueMember**|Aplikace Visual Studio nastaví tuto vlastnost na první sloupec, který je součástí primárního klíče, nebo na první sloupec v tabulce, pokud není definován žádný klíč.<br /><br /> Pokud je nutné provést úpravu, nastavte tuto vlastnost na primární klíč u tabulky se sloupcem, který chcete zobrazit.|  
    |**SelectedValue**|Visual Studio nastaví tuto vlastnost na původní sloupec vyřadit z **zdroje dat** okna.<br /><br /> Pokud je nutné provést úpravu, proveďte nastavení na sloupec cizího klíče v související tabulce.|  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vazby ovládacích prvků modelu Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
