---
title: 'Postupy: Vytvoření metod DataContext namapovaných na uložené procedury a funkce (O R Designer) | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: fa770c631e58fef47b6b44c33026ab9f27954238
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65685832"
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>Postupy: Vytvoření metod DataContext namapovaných na uložené procedury a funkce (O/R Designer)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Uložených procedur a funkcí lze přidat do [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] jako <xref:System.Data.Linq.DataContext> metody. Volání metody a předáním požadovaných parametrů v databázi Spustí uloženou proceduru nebo funkci a vrací data v návratovém typu <xref:System.Data.Linq.DataContext> metody. Podrobné informace o <xref:System.Data.Linq.DataContext> metody, naleznete v tématu [metod DataContext (O/R Designer)](../data-tools/datacontext-methods-o-r-designer.md).  
  
> [!NOTE]
> Uložené procedury lze také přepsat výchozí nastavení [!INCLUDE[vbtecdlinq](../includes/vbtecdlinq-md.md)] chování za běhu, který provádí vložení, aktualizace a odstranění při uložení změn z tříd entit k databázi. Další informace najdete v tématu [jak: Přiřazení uložených procedur za účelem aktualizace, vložení a odstranění (O/R Designer)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md).  
  
## <a name="creating-datacontext-methods"></a>Vytvoření metod DataContext  
 Můžete vytvořit <xref:System.Data.Linq.DataContext> metody přetažením uložené procedury nebo funkce z **Průzkumník serveru/Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
> [!NOTE]
> Návratový typ vytvořeného <xref:System.Data.Linq.DataContext> metoda se liší v závislosti na tom, kde vyřaďte uloženou proceduru nebo funkci na [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)]. Přetažení položek přímo do existující entity třídy vytvoří <xref:System.Data.Linq.DataContext> metoda s návratovým typem třídy entity. Přetažení položek na prázdnou oblast [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)] vytvoří <xref:System.Data.Linq.DataContext> metodu, která vrací automaticky generovanému typu. Můžete změnit návratový typ <xref:System.Data.Linq.DataContext> metoda po jeho přidání do podokna metody. Zkontrolovat nebo změnit návratový typ <xref:System.Data.Linq.DataContext> metoda, vyberte ho a zkontrolujte **návratový typ** vlastnost **vlastnosti** okna. Další informace najdete v tématu [jak: Změna návratového typu metody DataContext (O/R Designer)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
#### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>Chcete-li vytvořit DataContext metody, které vracejí automaticky vygenerovaných typů  
  
1. V **Průzkumníka serveru**/**Průzkumník databáze**, rozbalte **uložené procedury** uzel databáze pracujete.  
  
2. Vyhledejte požadovanou uložené procedury a přetáhněte ji na prázdnou oblast [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
     <xref:System.Data.Linq.DataContext> Metoda se vytvoří s automaticky generovanou návratový typ a zobrazí se v **metody** podokně.  
  
#### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>Vytvoření metod DataContext, které mají návratový typ třídy entity  
  
1. V **Průzkumníka serveru**/**Průzkumník databáze**, rozbalte **uložené procedury** uzel databáze pracujete.  
  
2. Vyhledejte požadovanou uložené procedury a přetáhněte ji na existující třídu entity v [!INCLUDE[vs_ordesigner_short](../includes/vs-ordesigner-short-md.md)].  
  
     <xref:System.Data.Linq.DataContext> Metoda s návratovým typem třídy vybranou entitu a je zahrnut v **metody** podokně.  
  
> [!NOTE]
> Informace o změnu návratového typu stávajících <xref:System.Data.Linq.DataContext> metody, naleznete v tématu [jak: Změna návratového typu metody DataContext (O/R Designer)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md).  
  
## <a name="see-also"></a>Viz také  
 [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [Metody DataContext (O/R Designer)](../data-tools/datacontext-methods-o-r-designer.md)   
 [Návod: Vytvoření třídy LINQ to SQL (Návrhář O-R)](https://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [Technologie LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)   
 [Úvod do LINQ v JAZYKU Visual Basic](https://msdn.microsoft.com/library/3047d86e-0d49-40e2-928b-dc02e46c7984)   
 [Postupy: Zápis dotazů LINQ vC#](https://msdn.microsoft.com/library/45e47fcc-cfa1-4b72-b161-d038ae87bd23)
