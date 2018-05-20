---
title: Volání kódu v doplňcích VSTO z jiných řešení pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VBA [Office development in Visual Studio], calling code in application-level add-ins
- application-level add-ins [Office development in Visual Studio], calling code from other solutions
- calling add-in code
- add-ins [Office development in Visual Studio], calling code from other solutions
- interoperability [Office development in Visual Studio]
- calling code from VBA
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 982fa23fa933bbade63222b78d677b88680601fc
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="call-code-in-vsto-add-ins-from-other-office-solutions"></a>Volání kódu v doplňcích VSTO z jiných řešení pro systém Office
  Objekt můžou zpřístupnit v doplňku VSTO do jiných řešení, včetně jiných řešení pro Microsoft Office. To je užitečné, pokud vaše doplňku VSTO poskytuje službu, která chcete povolit jiné řešení použít. Například pokud máte doplňku VSTO pro aplikaci Microsoft Office Excel, který provádí výpočtů finančních dat z webové služby, jiná řešení můžete provést tyto výpočty volání do doplněk aplikace Excel VSTO za běhu.  
  
 [!INCLUDE[appliesto_allapp](../vsto/includes/appliesto-allapp-md.md)]  
  
 Existují dva hlavní kroky v tomto procesu:  
  
-   Ve vašem Add-in VSTO vystavit objekt pro jiné řešení.  
  
-   V jiném řešení přístup k objektu vystavené vaší doplňku VSTO a členy volání objektu.  
  
## <a name="types-of-solutions-that-can-call-code-in-an-add-in"></a>Typy řešení, které můžete volání kódu v doplňku  
 Můžou zpřístupnit objekt VSTO Add-in pro následující typy řešení:  
  
-   Kódu Visual Basic for Applications (VBA) v dokumentu, který je načten do procesu aplikace jako vaše doplňku VSTO.  
  
-   Úpravy na úrovni dokumentů, které jsou načtené v rámci jednoho procesu aplikace jako vaše doplňku VSTO.  
  
-   Další doplňků VSTO vytvořen pomocí šablony projektů Office v sadě Visual Studio.  
  
-   Doplňků COM VSTO (tedy doplňků VSTO které implementují <xref:Extensibility.IDTExtensibility2> přímo rozhraní).  
  
-   Žádné řešení, které běží v jiném procesu než vaše doplňku VSTO (i s názvem tyto typy řešení *klienti mimo proces*). Patří mezi ně aplikace, které automatizují aplikaci Office, jako je Windows Forms nebo konzolové aplikace a doplňků VSTO načtené v jiném procesu.  
  
## <a name="expose-objects-to-other-solutions"></a>Vystavení objektů do jiných řešení  
 Ke zveřejnění na objekt v doplňku VSTO pro jiné řešení, proveďte následující kroky v doplňku VSTO:  
  
1.  Definice třídy, která chcete vystavit na jiné řešení.  
  
2.  Přepsání <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> metoda v `ThisAddIn` třídy. Vrátí instanci třídy, kterou chcete vystavit na jiné řešení.  
  
### <a name="define-the-class-you-want-to-expose-to-other-solutions"></a>Definice třídy, na kterou chcete vystavit do jiných řešení  
 Minimálně musí být třída, kterou chcete vystavit veřejné, musí mít <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut nastaven na **true**, a musí vystavit [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) rozhraní.  
  
 Doporučeným způsobem, jak vystavit [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) rozhraní je provést následující kroky:  
  
1.  Definujte rozhraní, který deklaruje členy, kteří chtějí zpřístupnit jiných řešení. Toto rozhraní můžete definovat v projektu doplňku VSTO. Můžete ale chtít definovat toto rozhraní v projektu knihovny samostatné třídy, pokud chcete vystavit třídy pro jiný VBA řešení, tak, aby řešení, které volají vaše doplňku VSTO může odkazovat na rozhraní bez odkazující na projektu doplňku VSTO.  
  
2.  Použít <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut toto rozhraní a nastavte tento atribut na **true**.  
  
3.  Upravte vlastní třídy pro toto rozhraní implementovat.  
  
4.  Použít <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atribut na třídu a nastavte tento atribut **žádné** hodnotu <xref:System.Runtime.InteropServices.ClassInterfaceType> – výčet.  
  
5.  Pokud chcete vystavit Tato třída klientům mimo proces, budete také muset postupujte takto:  
  
    -   Odvození třídy z <xref:System.Runtime.InteropServices.StandardOleMarshalObject>. Další informace najdete v tématu [vystavit třídy klientům mimo proces](#outofproc).  
  
    -   Nastavte **zaregistrovat zprostředkovatel komunikace s objekty COM** vlastnost v projektu, ve které definujete rozhraní. Tato vlastnost je nutné pouze v případě, že chcete klientům povolit používat časná vazba provést volání do doplňku VSTO.  
  
 Následující příklad kódu ukazuje `AddInUtilities` třídy s `ImportData` metoda, kterou lze volat pomocí jiných řešení. Tento kód v kontextu větší návod najdete v sekci [návod: volání kódu v doplňku VSTO z jazyka VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
 [!code-csharp[Trin_AddInInteropWalkthrough #3](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/AddInUtilities.cs#3)]
 [!code-vb[Trin_AddInInteropWalkthrough#3](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/AddInUtilities.vb#3)]  
  
### <a name="expose-classes-to-vba"></a>Vystavení třídy pro jazyk VBA  
 Když provedete podle kroků uvedených výše, VBA kód můžete volat pouze metody, které je deklarovat v rozhraní. VBA kód nelze volat jiné metody ve třídě, včetně metody, které třídě získá ze základní třídy, jako <xref:System.Object>.  
  
 Případně můžete vystavit [IDispatch](https://msdn.microsoft.com/library/windows/desktop/ms221608.aspx) rozhraní nastavením <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> atribut vazby AutoDispatch nebo AutoDual hodnotu <xref:System.Runtime.InteropServices.ClassInterfaceType> – výčet. Pokud vystavit rozhraní nemáte metody v samostatné rozhraní deklarovat. VBA kód však můžete volat žádné veřejné a nestatické metody ve třídě, včetně metody získat ze základní třídy, jako <xref:System.Object>. Kromě toho mimo proces klienty, kteří používají časná vazba nelze volat třídě.  
  
###  <a name="outofproc"></a> Vystavení třídy klientům mimo proces  
 Pokud chcete vystavit třídu v doplňku VSTO klientům mimo proces, by měl být odvozen z třídy <xref:System.Runtime.InteropServices.StandardOleMarshalObject> zajistit, aby klienti mimo proces můžete volat zveřejněné objektu doplňku VSTO. Pokusí se získat instanci objektu zveřejněné v klientovi mimo proces, jinak může neočekávaně selhat.  
  
 Tato chyba je vzhledem k tomu, že všechna volání do modelu objektu aplikace systému Office musí být provedeny na hlavního vlákna uživatelského rozhraní, ale volání z klienta mimo proces k objektu budou doručeny na zřetězení libovolný RPC (vzdálené volání procedur). Zařazování mechanismus COM v rozhraní .NET Framework nebude přepínat vláken a místo toho pokusí se zařazování volání objektu na příchozí vlákno RPC místo hlavního vlákna uživatelského rozhraní. Pokud je vaše objekt instancí třídy, která je odvozena od <xref:System.Runtime.InteropServices.StandardOleMarshalObject>, příchozí volání do objektu přeuspořádány automaticky na vlákno, kde zveřejněné objekt byl vytvořen, který bude hlavního vlákna uživatelského rozhraní aplikace hostitele.  
  
 Další informace o používání vláken v řešeních pro systém Office, najdete v části [podpora v Office práce s vlákny](../vsto/threading-support-in-office.md).  
  
### <a name="override-the-requestcomaddinautomationservice-method"></a>Potlačí metodu RequestComAddInAutomationService  
 Následující příklad kódu ukazuje, jak lze přepsat <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> v `ThisAddIn` třídy v doplňku VSTO. Příklad předpokládá, že jste definovali třídy s názvem `AddInUtilities` , kterou chcete vystavit na jiné řešení. Tento kód v kontextu větší návod najdete v sekci [návod: volání kódu v doplňku VSTO z jazyka VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
 [!code-csharp[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/CSharp/Trin_AddInInteropWalkthrough/ThisAddIn.cs#1)]
 [!code-vb[Trin_AddInInteropWalkthrough#1](../vsto/codesnippet/VisualBasic/Trin_AddInInteropWalkthrough/ThisAddIn.vb#1)]  
  
 Pokud vaše doplňku VSTO je načtena, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] volání <xref:Microsoft.Office.Tools.AddInBase.RequestComAddInAutomationService%2A> metoda. Modul runtime přiřadí vrácený objekt, který má <xref:Microsoft.Office.Core.COMAddIn.Object%2A> vlastnost <xref:Microsoft.Office.Core.COMAddIn> objekt, který reprezentuje vaše doplňku VSTO. To <xref:Microsoft.Office.Core.COMAddIn> objekt je k dispozici v dalších řešeních pro systém Office a řešení, které automatizují Office.  
  
## <a name="access-objects-from-other-solutions"></a>Přístup k objektům z jiných řešení  
 Volání zveřejněné objektu v doplňku VSTO, proveďte následující kroky v řešení pro klienta:  
  
1.  Získat <xref:Microsoft.Office.Core.COMAddIn> objekt, který reprezentuje zveřejněné VSTO doplněk. Klienti mají přístup ke všem Add in k dispozici VSTO pomocí `Application.COMAddIns` vlastnost v objektu modelu hostitele aplikace Office.  
  
2.  Přístup <xref:Microsoft.Office.Core.COMAddIn.Object%2A> vlastnost <xref:Microsoft.Office.Core.COMAddIn> objektu. Tato vlastnost vrací objekt zveřejněné z doplňku VSTO.  
  
3.  Volání členy zveřejněné objektu.  
  
 Způsob, jakým používáte vrácenou hodnotu <xref:Microsoft.Office.Core.COMAddIn.Object%2A> vlastnost se liší pro klienty VBA a bez VBA pro vytváření. Další kód pro klienty mimo proces, je nezbytné, aby se zabránilo možné časování.  
  
### <a name="access-objects-from-vba-solutions"></a>Přístup k objektům z řešení VBA  
 Následující příklad kódu ukazuje, jak používat VBA pro volání metody, který je zveřejněný prostřednictvím doplňku VSTO. Toto makro VBA volá metodu s názvem `ImportData` která je definovaná v Add-in VSTO, který je pojmenován **ExcelImportData**. Tento kód v kontextu větší návod najdete v sekci [návod: volání kódu v doplňku VSTO z jazyka VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md).  
  
```vb
Sub CallVSTOMethod()  
    Dim addIn As COMAddIn  
    Dim automationObject As Object  
    Set addIn = Application.COMAddIns("ExcelImportData")  
    Set automationObject = addIn.Object  
    automationObject.ImportData  
End Sub  
```  
  
### <a name="access-objects-from-non-vba-solutions"></a>Přístup k objektům z jiných VBA řešení  
 V jiných VBA řešení, musíte vysílat <xref:Microsoft.Office.Core.COMAddIn.Object%2A> vlastnost hodnotu implementuje rozhraní ho a pak můžete volat metodu zveřejněné na objekt rozhraní. Následující příklad kódu ukazuje způsob volání `ImportData` metoda z různých VSTO Add-in vytvořené pomocí doplňku Office developer tools v sadě Visual Studio.  
  
```vb  
Dim addIn As Office.COMAddIn = Globals.ThisAddIn.Application.COMAddIns.Item("ExcelImportData")  
Dim utilities As ExcelImportData.IAddInUtilities = TryCast( _  
    addIn.Object, ExcelImportData.IAddInUtilities)  
utilities.ImportData()  
```  
  
```csharp  
object addInName = "ExcelImportData";  
Office.COMAddIn addIn = Globals.ThisAddIn.Application.COMAddIns.Item(ref addInName);  
ExcelImportData.IAddInUtilities utilities = (ExcelImportData.IAddInUtilities)addIn.Object;  
utilities.ImportData();  
```  
  
 V tomto příkladu, pokud se pokusíte převést hodnotu <xref:Microsoft.Office.Core.COMAddIn.Object%2A> vlastnost, která má `AddInUtilities` třída místo `IAddInUtilities` rozhraní, vyvolá výjimku kód <xref:System.InvalidCastException>.  
  
## <a name="see-also"></a>Viz také  
 [Program doplňků VSTO](../vsto/programming-vsto-add-ins.md)   
 [Návod: Volání kódu v doplňku VSTO z jazyka VBA](../vsto/walkthrough-calling-code-in-a-vsto-add-in-from-vba.md)   
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Přizpůsobení funkcí uživatelského rozhraní pomocí rozšiřujících rozhraní](../vsto/customizing-ui-features-by-using-extensibility-interfaces.md)  
  
  