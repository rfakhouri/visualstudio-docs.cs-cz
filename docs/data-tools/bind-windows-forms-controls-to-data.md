---
redirect_url: /visualstudio/data-tools/bind-windows-forms-controls-to-data-in-visual-studio
ms.openlocfilehash: 5ba8ada294275a99aab27ff9c249d6c3d8e17da3
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
Title: "ovládací prvky Windows Forms vazby na data | Microsoft Docs"ms.custom:" "ms.date: ms.reviewer" 11/04/2016":" "ms.suite:" "ms.tgt_pltfrm:" "ms.topic:"článku"helpviewer_keywords: 
  - "zobrazení dat, Windows Forms – ovládací prvky"
  - "Windows Forms zobrazení dat"
  - "zdroje dat, zobrazení"
  - "data [Windows Forms] ve zobrazení" ms.assetid: 0163a34a-38cb-40b9-8f38-3058a90caf21 caps.latest.revision: 28 Autor: ms.author "gewarren": "gewarren" správce: ghogen ms.technology: "vs nástrojů data"
---
# <a name="bind-windows-forms-controls-to-data"></a>Vytvoření vazby ovládacích prvků Windows Forms k datům
Zdroje dat můžete vázat na ovládací prvky přetažením objektů ze **zdroje dat** okno na formuláři Windows nebo do existujícího ovládacího prvku ve formuláři. Před přetahování položek, můžete nastavit typ ovládacího prvku, který chcete vytvořit vazbu na. V závislosti na tom, zda zvolíte tabulky sám sebe nebo u jednotlivých sloupců se zobrazují různé hodnoty.  Můžete také nastavit vlastní hodnoty. Pro tabulku "Podrobnosti" znamená, že každý sloupec je vázána na samostatné ovládacího prvku.  

![Svázat zdroj dat se DataGridView](../data-tools/media/raddata-bind-data-source-to-datagridview.png "raddata vazby zdroje dat ovládacího prvku DataGridView")  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="bind-to--data-in-a-datagridview-control"></a>Vázání dat v ovládacím prvku DataGridView  
Pro DataGridView celá tabulka je vázána na daný jeden ovládací prvek. Při přetažení DataGridView do formuláře, nástroj pruhu pro procházení záznamů (<xref:System.Windows.Forms.BindingNavigator>) se zobrazí také. A [datovou sadu](../data-tools/dataset-tools-in-visual-studio.md), [TableAdapter](../data-tools/create-and-configure-tableadapters.md), <xref:System.Windows.Forms.BindingSource>, a <xref:System.Windows.Forms.BindingNavigator> se zobrazí v okně komponent. Na následujícím obrázku je TableAdapterManager také přidat, protože tabulka Zákazníci má vztah k tabulce objednávky. Tyto proměnné jsou všechny deklarované v automaticky vygenerovaný kód jako soukromé členy v třídě formuláře. Automaticky generovaný kód pro naplnění ovládacího prvku DataGridView se nachází v obslužné rutině události form_load. Kód pro ukládání dat k aktualizaci databáze se nachází v obslužné rutině události uložit pro objektu BindingNavigator. Můžete přesunout nebo upravit tento kód, podle potřeby.  
  
 ![Rutina GridView s BindingNavigator](../data-tools/media/raddata-gridview-with-bindingnavigator.png "raddata GridView s BindingNavigator")  
  
 Kliknutím na inteligentní značky v pravém horním rohu každé lze přizpůsobit chování ovládacího prvku DataGridView a objektu BindingNavigator:  
  
 ![DataGridView – a vytvoření vazby Navigátor inteligentních značek](../data-tools/media/raddata-datagridview-and-binding-navigator-smart-tags.png "raddata DataGridView a vytvoření vazby Navigátor inteligentní značky")  
  
 Pokud ovládací prvky aplikace vyžaduje nejsou dostupné v rámci **zdroje dat** okno, můžete přidat ovládací prvky. Další informace najdete v tématu [přidat vlastní ovládací prvky do okna zdroje dat](../data-tools/add-custom-controls-to-the-data-sources-window.md).  
  
 Můžete také přetáhnout položky z **zdroje dat** oken na ovládací prvky již ve formuláři pro vytvoření vazby ovládacího prvku k datům. Ovládací prvek, který je již vázána na data má jeho data, která vazby obnovit položky naposledy přetáhli ho. Být cílů platné umístění, musí být schopná zobrazit základní datový typ položky taženou do z ovládacích prvků **zdroje dat** okno. Například není platný přetáhněte položku, která má datový typ <xref:System.DateTime> na <xref:System.Windows.Forms.CheckBox>, protože <xref:System.Windows.Forms.CheckBox> není schopná zobrazit datum.  
  
## <a name="bind-to--data-in-individual-controls"></a>Vázání dat v jednotlivých ovládacích prvků  
 Při vytvoření vazby zdroje dat na "Podrobnosti", každý sloupec v datové sadě je svázán s ovládacím samostatné.  
  
 ![Svázat zdroj dat se podrobnosti](../data-tools/media/raddata-bind-data-source-to-details.png "raddata vazby zdroje dat podrobnosti")  
  
> [!IMPORTANT]
>  Všimněte si, že na předchozím obrázku, přetáhněte z vlastnosti objednávek zákazníků tabulky, není v této tabulce. Pomocí vazby pro vlastnost Customer.Orders navigační příkazy provedené v ovládacím prvku DataGridView okamžitě se projeví v ovládacích prvcích podrobnosti. Pokud jste přetáhli v tabulce, ovládací prvky by být stále vázaná k datové sadě, ale nemohli je synchronizovány s ovládacím prvku DataGridView.  
  
 Následující obrázek znázorňuje výchozí ovládací prvky vázané na data, které jsou přidány do formuláře po vlastnost objednávky v tabulce Zákazníci je vázána na "Podrobnosti" v **zdroje dat** okno.  
  
 ![Tabulka objednávky vázána na podrobnosti o](../data-tools/media/raddata-orders-table-bound-to-details.png "tabulky objednávky raddata vázána na podrobnosti")  
  
 Všimněte si také, zda má každý ovládací prvek inteligentních značek. Tato značka umožňuje úpravy, které platí pro pouze tento ovládací prvek.  
  
## <a name="see-also"></a>Viz také  
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)