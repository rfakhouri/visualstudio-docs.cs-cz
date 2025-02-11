---
title: Vytvoření vazby ovládacích prvků modelu Windows Forms k datům
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
- data [Windows Forms], data sources
- Windows Forms, data binding
- Windows Forms, displaying data
- displaying data on forms
- forms, displaying data
- data sources, displaying data
- displaying data, Windows Forms
- data [Windows Forms], displaying
ms.assetid: 243338ef-41af-4cc5-aff7-1e830236f0ec
caps.latest.revision: 40
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 07c5853b673657c3ce8e90467a13bbac3f430b6e
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65698991"
---
# <a name="bind-windows-forms-controls-to-data-in-visual-studio"></a>Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Uživatelům vaší aplikace můžete zobrazit data pomocí vazby dat do formulářů Windows. Pokud chcete vytvořit tyto ovládací prvky vázané na data, můžete přetáhnout položky z **zdroje dat** okna do Návrháře formulářů Windows v sadě Visual Studio. Toto téma popisuje některé nejběžnější úlohy, nástroje a třídy účastnící se vytváření aplikací pro Windows Forms vázané na data.

 ![Zdroj dat přetáhnout operace](../data-tools/media/raddata-data-source-drag-operation.png "operace přetažení raddata zdroj dat")

 Obecné informace o tom, jak vytvořit ovládací prvky vázané na data v sadě Visual Studio najdete v tématu [vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md). Další informace o datové vazbě ve formulářích Windows najdete v tématu [Windows Forms – datová vazba](https://msdn.microsoft.com/library/c3826d8e-ea25-4ad4-a669-45bfb19192aa).

## <a name="in-this-section"></a>V tomto oddílu

- [Vytvoření vazby ovládacích prvků modelu Windows Forms k datům](../data-tools/bind-windows-forms-controls-to-data.md)

- [Potvrzení úprav v procesu v ovládacích prvcích vázaných na data před uložením dat](../data-tools/commit-in-process-edits-on-data-bound-controls-before-saving-data.md)

- [Vytváření vyhledávacích tabulek v aplikacích modelu Windows Forms](../data-tools/create-lookup-tables-in-windows-forms-applications.md)

- [Vytvoření formuláře Windows k vyhledávání dat](../data-tools/create-a-windows-form-to-search-data.md)

- [Vytvoření uživatelského ovládacího prvku modelu Windows Forms, který podporuje jednoduchou datovou vazbu](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md)

- [Vytvoření uživatelského ovládacího prvku modelu Windows Forms, který podporuje složitou datovou vazbu](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md)

- [Vytvoření uživatelského ovládacího prvku modelu Windows Forms, který podporuje vazbu vyhledávacích dat](../data-tools/create-a-windows-forms-user-control-that-supports-lookup-data-binding.md)

- [Předávání dat mezi formuláři](../data-tools/pass-data-between-forms.md)

## <a name="bindingsource-component"></a>BindingSource – komponenta
 <xref:System.Windows.Forms.BindingSource> Komponenta má dva účely. Nejprve poskytuje abstrakční vrstvu při vytvoření vazby ovládacích prvků na formuláři na data. Ovládací prvky ve formuláři je vázána na <xref:System.Windows.Forms.BindingSource> komponentu (namísto svázaný se přímo ke zdroji dat).

 Za druhé je možné spravovat kolekci objektů. Přidání typu <xref:System.Windows.Forms.BindingSource> vytvoří seznam daného typu.

 Další informace o <xref:System.Windows.Forms.BindingSource> komponenty, naleznete v tématu:

- [Komponenta BindingSource](https://msdn.microsoft.com/library/3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9)

- [Přehled komponenty BindingSource](https://msdn.microsoft.com/library/be838caf-fcb0-4b68-827f-58b2c04b747f)

- [Architektura komponenty BindingSource](https://msdn.microsoft.com/library/7bc69c90-8a11-48b1-9336-3adab5b41591)

## <a name="bindingnavigator-control"></a>BindingNavigator – ovládací prvek
 Tato součást poskytuje uživatelské rozhraní pro procházení dat zobrazených v aplikaci Windows. Další informace najdete v tématu [BindingNavigator – ovládací prvek](https://msdn.microsoft.com/library/18c1e2a5-9834-40d3-9b2e-2b545e4e769e).

## <a name="datagridview-control"></a>DataGridView – ovládací prvek
 Chcete-li zobrazit a upravit tabulková data z mnoha různých druhů zdrojů dat, použijte <xref:System.Windows.Forms.DataGridView> ovládacího prvku. Můžete svázat data <xref:System.Windows.Forms.DataGridView> pomocí <xref:System.Windows.Forms.DataGridView.DataSource%2A> vlastnost. Další informace najdete v tématu [Přehled ovládacího prvku DataGridView](https://msdn.microsoft.com/library/0a45c661-89dc-4390-9cc6-c47eee501488).

## <a name="see-also"></a>Viz také
 [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)
