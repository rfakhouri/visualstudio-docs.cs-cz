---
title: Omezení ovládacích prvků Windows Forms v dokumentech Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio, Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], ActiveX legacy
- ActiveX controls [Office development in Visual Studio]
- Windows Forms controls [Office development in Visual Studio], limitations
- controls [Office development in Visual Studio], Windows Forms controls
- Windows Forms controls [Office development in Visual Studio], unsupported properties and methods
- Toolbox [Office development in Visual Studio], unsupported controls
- user controls [Office development in Visual Studio], grouping controls
- Windows Forms controls [Office development in Visual Studio], Toolbox
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: d5cb4bf5788e1d30933a807e2e97e064118fc076
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67823411"
---
# <a name="limitations-of-windows-forms-controls-on-office-documents"></a>Omezení ovládacích prvků Windows Forms v dokumentech Office

Existují určité rozdíly mezi ovládacími prvky Windows Forms, které jsou přidány do dokumentů aplikace Microsoft Office Word nebo sešitů aplikace Microsoft Office Excel a ovládací prvky Windows Forms, které jsou přidány do formulářů Windows. Například když přidáte <xref:Microsoft.Office.Tools.Word.Controls.Button> ovládací prvek dokumentu, vlastnosti, jako <xref:System.Windows.Forms.Control.Dock>, <xref:System.Windows.Forms.Control.Anchor>, a <xref:System.Windows.Forms.Control.TabIndex> nefungují tak, jak byste asi očekávali.

Mnohé z těchto rozdílů jsou způsobeny tím, jak tento Windows Forms, ovládací prvky jsou hostované v dokumentech. Při přidání ovládacího prvku Windows Forms do dokumentů, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] vloží ovládací prvek ActiveX, který je hostitelem pak ovládacího prvku Windows Forms v dokumentu. Ovládacího prvku Windows Forms se vloží přímo do dokumentu.

[!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]

## <a name="limitations-of-methods-and-properties-of-windows-forms-controls"></a>Omezení metod a vlastností ovládacích prvků Windows Forms

Existuje několik metod a vlastností ovládacích prvků Windows Forms, které nefungují stejně jako v dokumentu, jako kdyby je sdíleli ve formuláři Windows Forms, a proto se doporučuje, nelze použít. Například nastavení vlastností <xref:System.Windows.Forms.Control.Dock> a <xref:System.Windows.Forms.Control.Anchor> ovlivní pouze pozice ovládacího prvku s ohledem na ovládací prvek ActiveX v kontejneru, nikoli dokumentu. Následuje seznam nepodporovaných metod a vlastností ovládacích prvků Windows Forms pro aplikace Word a Excel:

- Nepodporované vlastnosti ovládacích prvků aplikace Excel:

  - <xref:System.Windows.Forms.Control.Anchor>
  - <xref:System.Windows.Forms.Control.Dock>
  - <xref:System.Windows.Forms.Control.Location>
  - <xref:System.Windows.Forms.Control.TabIndex>
  - <xref:System.Windows.Forms.Control.TabStop>
  - <xref:System.Windows.Forms.Control.TopLevelControl>

- Nepodporovaných metod a vlastností ovládacích prvků aplikace Word:

  - <xref:System.Windows.Forms.Control.Hide%2A>
  - <xref:System.Windows.Forms.Control.Show%2A>
  - <xref:System.Windows.Forms.Control.Anchor>
  - <xref:System.Windows.Forms.Control.Dock>
  - <xref:System.Windows.Forms.Control.Location>
  - <xref:System.Windows.Forms.Control.TabIndex>
  - <xref:System.Windows.Forms.Control.TabStop>
  - <xref:System.Windows.Forms.Control.TopLevelControl>
  - <xref:System.Windows.Forms.Control.Visible>

Také nelze nastavit <xref:System.Windows.Forms.Control.Left> nebo <xref:System.Windows.Forms.Control.Top> vlastnosti ovládacích prvků Windows Forms, které jsou v textu ve Wordovém dokumentu. Ovládací prvky Windows Forms jsou přidány v textu v následujících případech:

- Přidání ovládacího prvku do dokumentu aplikace Word prostřednictvím kódu programu a použít metodu, která určuje rozsah pro umístění.

- Přidáte ovládacího prvku Windows Forms do dokumentů aplikace Word v době návrhu. Můžete to změnit úpravou ovládací prvek v návrháři.

## <a name="differences-in-windows-forms-controls-on-office-documents"></a>Rozdíly v ovládacích prvcích Windows Forms v dokumentech Office

Ovládacích prvků Windows Forms obecně mají stejné chování v dokumentu systému Office, jako jsou ve formuláři Windows Forms, ale existuje několik rozdílů. Následující tabulka popisuje rozdíly, která platí pro ovládací prvky Windows Forms v dokumentech Office.

|Funkce|Rozdíl|
|-------------------|----------------|
|Pořadí ovládacího prvku|Pomocí ovládacích prvků umístit sešitu aplikace Excel nebo Wordový dokument nelze tabulátoru.|
|Ovládací prvek seskupení|Nelze použít <xref:System.Windows.Forms.GroupBox> ovládací prvek obsahující další ovládací prvky v dokumentu systému Office. Když přidáte vícenásobných přepínačů přímo do dokumentu, mají přepínací tlačítka se vzájemně nevylučují. Můžete napsat kód, který přepínačů vzájemně vylučují. Upřednostňovaný způsob je však k přidání tlačítek přepínače do uživatelského ovládacího prvku a poté přidat uživatelský ovládací prvek v dokumentu. Další informace najdete v tématu ukázková ovládací prvky aplikace Word nebo Excel Ukázky ovládacích prvků na [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).|
|Typ ovládacího prvku|Ovládací prvky Windows Forms používané na dokumenty jsou zabaleny ve třídě poskytuje [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] udávající další funkce, které jsou specifické pro ovládací prvky do listu aplikace Excel nebo dokument aplikace Word. Pokud máte například **tlačítko** ovládání na listu aplikace Excel, je nutné zadat typ jako <xref:Microsoft.Office.Tools.Excel.Controls.Button> spíše než <xref:System.Windows.Forms.Button> při odkazování na nebo přetypováním objektu.|
|Ovládací prvek pozice a velikost|Velikost a umístění ovládacího prvku je určeno vlastností, které jsou součástí kontejneru ovládacího prvku ActiveX. Vlastnosti ovládacích prvků ActiveX trvat jiné hodnoty než ekvivalentní vlastnosti ovládacího prvku Windows Forms. Při nastavení `Top`, `Left`, `Height`, nebo `Width` vlastností ovládacího prvku, se měří v odkazuje, nikoli pixelů.|
|Pozice ovládacího prvku na dokumenty aplikace Word|Pokud přidáte ovládací prvky do rozložení na základě toku, mějte na paměti, který ovládací prvky budou směrovat s obsahem jako změny obsahu. Ovládací prvek odstavce nelze ukotvit, při přetažení z **nástrojů** vzhledem k tomu, že ovládací prvek je přidán do dokumentu aplikace Word v textu. Pokud používáte jinou metodu přidejte ovládací prvek, jako je například poklepání ovládací prvek, ovládací prvek je vložen podle možnosti slovo, které jste nastavili pro vkládání obrázků.<br /><br /> Nelze nastavit `Left` nebo `Top` vlastnost ovládacího prvku, který je vložený v textu.<br /><br /> Ovládací prvky nelze umístit v záhlaví nebo zápatí stránky, nebo v rámci vnořeného dokumentu.|
|Události ovládacích prvků|Při výběru ovládacího prvku vyvolává události v uvedeném pořadí:<br /><br /> 1.  `Enter`<br />2.  `GotFocus`<br /><br /> Když ovládací prvek není vybraná, vyvolává události v uvedeném pořadí:<br /><br /> 1.  `Leave`<br />2.  `Validating`<br />3.  `Validated`<br />4.  `LostFocus`|
|Změna velikosti ovládacího prvku|Když změníte nastavení přiblížení dokumentu na něco jiného než 100 %, ovládací prvky jsou zakázány, i když jsou uvedeny na škálování s dokumentem. Například pokud klepnutí na tlačítko, pokud váš dokument je na 130 % přiblížení, zobrazí se zpráva, že ovládací prvek byl zakázán, dokud se nenastaví zvětšení na 100 %. Ovládací prvky bude program fungovat správně při změně zvětšení na 100 %.|
|Hodnoty vlastností ovládacího prvku|I když vlastností ovládacích prvků ve formuláři Windows Forms jsou nastaveny na celočíselnou hodnotu, jsou nastaveny do jediné pro ovládací prvky ve Wordovém dokumentu. V aplikaci Excel jsou nastaveny hodnoty vlastností ovládacích prvků na dvojitou hodnotu. Pokud `Height` a `Width` vlastnost ovládacího prvku na listu je větší než velikost listu nebo obrazovky, hodnota je oříznutá.|
|Změna velikosti ovládacího prvku|Pokud změníte velikost ovládacího prvku na dokument pomocí jednoho z úchytů osm, nový ovládací prvek dimenze se neprojeví v **vlastnosti** okna, dokud je znovu vybrány ovládacího prvku.|
|Chování ovládacího prvku|Rozdělit okno Sešit může být nepředvídatelné chování ovládacích prvků na list aplikace Excel. Například přístup k <xref:Microsoft.Office.Tools.Excel.Controls.TextBox> na listu může být k dispozici pouze v jednom ze systému windows.|
|Názvy ovládacího prvku|Název ovládacích prvků vyhrazená slova nelze použít. Například, pokud chcete přidat <xref:Microsoft.Office.Tools.Excel.Controls.Button> do listu a změňte název na **systému**, dojde k chybám při sestavení projektu.|
|Programové přidání ovládacích prvků|Nepoužívejte konstruktoru ovládacího prvku k přidání ovládacího prvku do dokumentu za běhu. Místo toho použijte pomocné metody poskytované objektem [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]. Například použít <xref:Microsoft.Office.Tools.Excel.ControlExtensions.AddButton%2A> způsob, jak přidat tlačítko do listu. Pokud chcete přidat ovládací prvek, který nepodporuje tyto pomocné metody, můžete použít `AddControl` metody. Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).|
|Kopírování ovládacích prvků|Pokud zkopírujete ovládacího prvku Windows Forms a vložte ji do dokumentu za běhu, prázdný kontejner ovládacího prvku ActiveX je vložen do dokumentu. Ovládacího prvku Windows Forms se nezobrazí v novém umístění a kódu na pozadí původního ovládacího prvku není zkopírován do kontejneru ovládacího prvku ActiveX.|

## <a name="limitations-in-document-level-projects"></a>Omezení v projektech na úrovni dokumentu

Některá omezení pomocí ovládacích prvků Windows Forms v dokumentech jsou jedinečné pro projekty na úrovni dokumentu.

### <a name="control-support-at-design-time"></a>Podpora ovládacího prvku v době návrhu

Některé ovládací prvky Windows Forms jsou odebrány z **nástrojů** při sešitu aplikace Excel nebo Wordový dokument je otevřen v návrháři aplikace Visual Studio. Toto je z důvodu technická omezení nebo proto, že funkce je již k dispozici v aplikaci Word nebo Excel. Projekty aplikace Excel a Word podporují všechny ovládací prvky Windows Forms a další součásti, které se zobrazují v **nástrojů** když dokument má fokus, a můžete také přidat ovládací prvky třetích stran na listu nebo dokumentu.

> [!NOTE]
> Všechny ovládací prvky jsou odebrány z **nástrojů** když je dokument chráněný. Informace o ochraně dokumentů najdete v tématu [ochrana v řešeních na úrovni dokumentu dokument](../vsto/document-protection-in-document-level-solutions.md).

> [!NOTE]
> Ovládací prvky třetích stran, musíte mít <xref:System.Runtime.InteropServices.ComVisibleAttribute> atribut nastaven na **true** jinak se nedá použít v řešení pro Office.

Nejsou k dispozici v následujících ovládacích prvků a komponent **nástrojů**:

- <xref:System.Windows.Forms.BindingNavigator>

- <xref:System.Windows.Forms.ContextMenuStrip>

- <xref:System.Windows.Forms.DataGrid>

- <xref:System.DirectoryServices.DirectoryEntry>

- <xref:System.DirectoryServices.DirectorySearcher>

- <xref:System.Windows.Forms.ErrorProvider>

- <xref:System.Diagnostics.EventLog>

- <xref:System.IO.FileSystemWatcher>

- <xref:System.Windows.Forms.FlowLayoutPanel>

- <xref:System.Windows.Forms.GroupBox>

- <xref:System.Windows.Forms.MainMenu>

- <xref:System.Windows.Forms.MenuStrip>

- <xref:System.Messaging.MessageQueue>

- <xref:System.Windows.Forms.NotifyIcon>

- <xref:System.Windows.Forms.PageSetupDialog>

- <xref:System.Windows.Forms.Panel>

- <xref:System.Diagnostics.PerformanceCounter>

- <xref:System.Windows.Forms.PrintDialog>

- <xref:System.Drawing.Printing.PrintDocument>

- <xref:System.Windows.Forms.PrintPreviewControl>

- <xref:System.Diagnostics.Process>

- <xref:System.Windows.Forms.RichTextBox>

- <xref:System.IO.Ports.SerialPort>

- <xref:System.ServiceProcess.ServiceController>

- <xref:System.Windows.Forms.SplitContainer>

- <xref:System.Windows.Forms.Splitter>

- <xref:System.Windows.Forms.StatusBar>

- <xref:System.Windows.Forms.StatusStrip>

- <xref:System.Windows.Forms.TabControl>

- <xref:System.Windows.Forms.TableLayoutPanel>

- <xref:System.Timers.Timer>

- <xref:System.Windows.Forms.Timer>

- <xref:System.Windows.Forms.ToolBar>

- <xref:System.Windows.Forms.ToolStrip>

- <xref:System.Windows.Forms.ToolStripContainer>

- <xref:System.Windows.Forms.ToolStripDropDown>

- <xref:System.Windows.Forms.ToolStripDropDownMenu>

- <xref:System.Windows.Forms.ToolStripPanel>

### <a name="support-for-legacy-activex-controls"></a>Podpora pro starší verze – ovládací prvky ActiveX

Pokud vytvoříte projekt sady Office úrovni dokumentu, který používá existující dokument aplikace Word nebo sešit, který obsahuje ovládací prvky ActiveX, nedojde ke ztrátě; funkce ovládacích prvků ActiveX neexistuje ale žádná podpora pro přidání nových ovládacích prvků ActiveX do dokumentů z Visual Studia. Například, pokud má tlačítko z dokumentu aplikace Word **ovládací prvek** nástrojů, na kterém běží Visual Basic for Applications (VBA) – makro bude nadále spouštět makra po dokumentu se použil v projektu aplikace Office. Doporučujeme však odebrat ovládací prvky ActiveX a makra VBA a nahraďte ovládacích prvků Windows Forms a spravovaný kód.

## <a name="see-also"></a>Viz také:

- [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)
- [Ovládací prvky Windows Forms na dokumenty Office – přehled](../vsto/windows-forms-controls-on-office-documents-overview.md)
- [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)
- [Postupy: Přidání ovládacích prvků Windows Forms do dokumentů Office](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)
