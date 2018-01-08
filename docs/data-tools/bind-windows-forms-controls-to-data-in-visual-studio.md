---
title: "Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/03/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], data sources
- Windows Forms, data binding
- Windows Forms, displaying data
- displaying data on forms
- forms, displaying data
- data sources, displaying data
- displaying data, Windows Forms
- data [Windows Forms], displaying
ms.assetid: 243338ef-41af-4cc5-aff7-1e830236f0ec
caps.latest.revision: "37"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 7ade7aa6e103a8637d26b10029faabc434ce3a83
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="bind-windows-forms-controls-to-data-in-visual-studio"></a>Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio
Data můžete zobrazit uživatelům vaší aplikace pomocí vytvoření vazby dat do formulářů Windows. Chcete-li vytvořit tyto ovládací prvky vázané na data, můžete přetáhnout položky z **zdroje dat** okna do Windows Forms designerem v sadě Visual Studio.
  
![Zdroj dat přetáhněte operaci](../data-tools/media/raddata-data-source-drag-operation.png "raddata zdroj dat přetáhněte operace")

Před přetahování položek, můžete nastavit typ ovládacího prvku, který chcete vytvořit vazbu na. V závislosti na tom, zda zvolíte tabulky sám sebe nebo u jednotlivých sloupců se zobrazují různé hodnoty.  Můžete také nastavit vlastní hodnoty. Pro tabulku "Podrobnosti" znamená, že každý sloupec je vázána na samostatné ovládacího prvku.  

![Svázat zdroj dat se DataGridView](../data-tools/media/raddata-bind-data-source-to-datagridview.png "raddata vazby zdroje dat ovládacího prvku DataGridView")  
  
## <a name="bindingsource-and-bindingnavigator-controls"></a>BindingSource a BindingNavigator – ovládací prvky
<xref:System.Windows.Forms.BindingSource> Součást má dva účely. Nejprve poskytuje úroveň abstrakce, při vytváření vazby ovládacích prvků k datům. Ovládací prvky na formuláři je vázána na <xref:System.Windows.Forms.BindingSource> součásti místo přímo ke zdroji dat. Druhý umožňuje spravovat kolekce objektů. Přidání typu k <xref:System.Windows.Forms.BindingSource> vytvoří seznam daného typu.  
  
Další informace o <xref:System.Windows.Forms.BindingSource> součást, najdete v části:  
  
-   [Komponenta BindingSource](/dotnet/framework/winforms/controls/bindingsource-component)  
  
-   [Přehled komponenty BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-overview)  
  
-   [Architektura komponenty BindingSource](/dotnet/framework/winforms/controls/bindingsource-component-architecture)  
  
[BindingNavigator – ovládací prvek](/dotnet/framework/winforms/controls/bindingnavigator-control-windows-forms) poskytuje uživatelské rozhraní pro procházení dat, které zobrazuje aplikace systému Windows.

## <a name="bind-to-data-in-a-datagridview-control"></a>Vázání dat v ovládacím prvku DataGridView  
Pro [DataGridView – ovládací prvek](/dotnet/framework/winforms/controls/datagridview-control-overview-windows-forms), celá tabulka je vázána na daný jeden ovládací prvek. Při přetažení DataGridView do formuláře, nástroj pruhu pro procházení záznamů (<xref:System.Windows.Forms.BindingNavigator>) se zobrazí také. A [datovou sadu](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent. Na následujícím obrázku je TableAdapterManager také přidat, protože tabulka Zákazníci má vztah k tabulce objednávky. Tyto proměnné jsou všechny deklarované v automaticky vygenerovaný kód jako soukromé členy v třídě formuláře. Automaticky generovaný kód pro naplnění ovládacího prvku DataGridView se nachází v obslužné rutině události form_load. Kód pro ukládání dat k aktualizaci databáze se nachází v obslužné rutině události uložit pro objektu BindingNavigator. Můžete přesunout nebo upravit tento kód, podle potřeby.  
  
![Rutina GridView s BindingNavigator](../data-tools/media/raddata-gridview-with-bindingnavigator.png "raddata GridView s BindingNavigator")  
  
Kliknutím na inteligentní značky v pravém horním rohu každé lze přizpůsobit chování ovládacího prvku DataGridView a objektu BindingNavigator:  
  
![DataGridView – a vytvoření vazby Navigátor inteligentních značek](../data-tools/media/raddata-datagridview-and-binding-navigator-smart-tags.png "raddata DataGridView a vytvoření vazby Navigátor inteligentní značky")  
  
Pokud ovládací prvky aplikace vyžaduje nejsou dostupné v rámci **zdroje dat** okno, můžete přidat ovládací prvky. Další informace najdete v tématu [přidat vlastní ovládací prvky do okna zdroje dat](../data-tools/add-custom-controls-to-the-data-sources-window.md).  
  
Můžete také přetáhnout položky z **zdroje dat** oken na ovládací prvky již ve formuláři pro vytvoření vazby ovládacího prvku k datům. Ovládací prvek, který je již vázána na data má jeho data, která vazby obnovit položky naposledy přetáhli ho. Být cílů platné umístění, musí být schopná zobrazit základní datový typ položky taženou do z ovládacích prvků **zdroje dat** okno. Například není platný přetáhněte položku, která má datový typ <xref:System.DateTime> na <xref:System.Windows.Forms.CheckBox>, protože <xref:System.Windows.Forms.CheckBox> není schopná zobrazit datum.  
  
## <a name="bind-to-data-in-individual-controls"></a>Vázání dat v jednotlivých ovládacích prvků  
Při vytvoření vazby zdroje dat na "Podrobnosti", každý sloupec v datové sadě je svázán s ovládacím samostatné.  
  
![Svázat zdroj dat se podrobnosti](../data-tools/media/raddata-bind-data-source-to-details.png "raddata vazby zdroje dat podrobnosti")  
  
> [!IMPORTANT]
> Všimněte si, že na předchozím obrázku, přetáhněte z vlastnosti objednávek zákazníků tabulky, není v této tabulce. Pomocí vazby pro vlastnost Customer.Orders navigační příkazy provedené v ovládacím prvku DataGridView okamžitě se projeví v ovládacích prvcích podrobnosti. Pokud jste přetáhli v tabulce, ovládací prvky by být stále vázaná k datové sadě, ale nemohli je synchronizovány s ovládacím prvku DataGridView.  
  
Následující obrázek znázorňuje výchozí ovládací prvky vázané na data, které jsou přidány do formuláře po vlastnost objednávky v tabulce Zákazníci je vázána na "Podrobnosti" v **zdroje dat** okno.  
  
![Tabulka objednávky vázána na podrobnosti o](../data-tools/media/raddata-orders-table-bound-to-details.png "tabulky objednávky raddata vázána na podrobnosti")  
  
Všimněte si také, zda má každý ovládací prvek inteligentních značek. Tato značka umožňuje úpravy, které platí pro pouze tento ovládací prvek.
  
## <a name="see-also"></a>Viz také
[Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)  
[Datové vazby v systému Windows Forms (rozhraní .NET Framework)](/dotnet/framework/winforms/windows-forms-data-binding)