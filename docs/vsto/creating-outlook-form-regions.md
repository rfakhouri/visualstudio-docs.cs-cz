---
title: Vytváření oblastí formulářů aplikace Outlook
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- MICROSOFT.OFFICE.TOOLS.OUTLOOK.FORMREGION
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio]
- form regions [Office development in Visual Studio], creating
- Outlook [Office development in Visual Studio], form regions
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: bc8b1af95596ba182c69956155105a42f92212bb
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
ms.locfileid: "34265547"
---
# <a name="create-outlook-form-regions"></a>Vytváření oblastí formulářů aplikace Outlook
  Oblasti formuláře můžete použít k přizpůsobení formulářů aplikace Microsoft Office Outlook. Visual Studio poskytuje pokročilé nástroje, které bylo snazší pro vás k návrhu, vývoji a ladění oblasti formuláře.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Toto téma poskytuje následující informace:  
  
-   [Výhody používání oblasti formuláře](#Enhance)  
  
-   [Do projektu přidejte oblasti formuláře aplikace Outlook](#Adding)  
  
-   [Použití návrháře oblasti formuláře](#UsingFormRegionDesigner)  
  
-   [Použít oblasti formuláře navržené v aplikaci Outlook](#UsingFormRegionDesignedOutlook)  
  
-   [Přidat vlastní kód do oblasti formuláře](#AddingCustomCode)  
  
-   [Sestavení projektu](#Building)  
  
-   [Ladění oblasti formuláře](#Debugging)  
  
-   [Nasazení oblasti formuláře](#Deploying)  
  
##  <a name="Enhance"></a> Výhody používání oblasti formuláře  
 Oblasti formuláře nabízí mnoho vylepšení přes tradiční vývoje formulářů aplikace Outlook:  
  
-   Úprava výchozí stránky všechny standardní formuláře.  
  
-   Všechny standardní formuláře přidáte až 12 další stránky.  
  
-   Nahraďte nebo vylepšují všechny standardní formuláře.  
  
-   Uživatelské rozhraní zobrazí v podokně pro čtení a kontroly.  
  
 Další informace najdete v tématu [přizpůsobit stránky formuláře a oblasti formuláře](http://msdn.microsoft.com/library/office/ff869060.aspx).  
  
##  <a name="Adding"></a> Do projektu přidejte oblasti formuláře aplikace Outlook  
 Můžete použít **nové oblasti formuláře aplikace Outlook** Průvodce návrhu nové oblasti formuláře nebo import oblasti formuláře, který byl navržen v aplikaci Outlook. Navíc pokud máte oblasti formuláře, který jste použili v jiném projektu doplňku VSTO pro Outlook, můžete opakovaně použít vaše stávající oblasti formuláře.  
  
###  <a name="CreatingFormRegion"></a> Vytvoření nové oblasti formuláře pomocí Průvodce  
 Chcete-li vytvořit oblasti formuláře, přidejte **oblasti formuláře aplikace Outlook** položku do projektu doplňku VSTO v Outlooku. Tím se spustí **nové oblasti formuláře aplikace Outlook** průvodce.  
  
 Použijte průvodce k označení, zda chcete návrhu nové oblasti formuláře nebo import oblasti formuláře, který byl navržen v aplikaci Outlook. Další informace o návrhu nové oblasti formuláře najdete v tématu [použít Návrháře oblasti formuláře](#UsingFormRegionDesigner). Další informace o používání oblasti formuláře navržené v aplikaci Outlook najdete v tématu [Import oblasti formuláře navržené v aplikaci Outlook](#UsingFormRegionDesignedOutlook).  
  
 Zadejte typ oblasti formuláře, který chcete vytvořit pomocí průvodce. Následující tabulka popisuje každý typ oblasti formuláře.  
  
|Typ oblasti|Popis|  
|-----------------|-----------------|  
|Samostatné|Přidá oblasti formuláře jako novou stránku pomocí formuláře aplikace Outlook.|  
|Přiléhající|Oblasti formuláře se připojí k dolní části stránky výchozí pomocí formuláře aplikace Outlook.|  
|Nahrazení|Přidá oblasti formuláře jako novou stránku, která nahradí výchozí stránky formuláře aplikace Outlook.|  
|Nahraďte všechny|Oblasti formuláře nahradí celý formuláře aplikace Outlook.|  
  
 Průvodce můžete použít také k určení podmínek, zobrazení a vyberte typ formuláře k rozšíření. Další informace najdete v tématu [postupy: přidání oblasti formuláře do projektu doplněk aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
 Možnosti, které provedete v Průvodci ovlivňuje možnosti, které jsou k dispozici v dalších stránkách průvodce. Například, pokud vyberete **Adjoining** nebo **samostatné** v **vytvořit nové oblasti formuláře aplikace Outlook** stránky, pak se **název** a **Popis** pole jsou k dispozici v **zadejte popisný text a vybrat vaše předvolby zobrazení** stránky. Je to proto, že aplikace Outlook nepoužívá těchto polí, pokud se zobrazí sousedících nebo samostatné oblasti formuláře.  
  
#### <a name="form-region-files"></a>Soubory oblastí formulářů  
 Po dokončení **nové oblasti formuláře aplikace Outlook** průvodce, Visual Studio automaticky přidá následující soubory do projektu:  
  
-   Soubor kód oblasti formuláře. Tento soubor má název, který zadáte pro **oblasti formuláře aplikace Outlook** položky v **přidat novou položku** dialogové okno. Přidáte kód pro zpracování události oblasti formuláře do tohoto souboru.  
  
-   Soubor návrháře kód oblasti formuláře. Tento soubor obsahuje kód vygenerovaný Návrhář oblasti formuláře a by neměla být upravována přímo.  
  
-   Úložiště formuláře aplikace Outlook (*.ofs*) souboru.  
  
    > [!NOTE]  
    >  Tento soubor je přidat do projektu jenom v případě import oblasti formuláře, který byl navržen v aplikaci Outlook.  
  
#### <a name="form-region-factory-class"></a>Třídu objektů factory oblasti formuláře  
 Soubor kód oblasti formuláře obsahuje konkrétní třídu, která implementuje <xref:Microsoft.Office.Tools.Outlook.IFormRegionFactory> rozhraní. Toto je třída objektu pro vytváření oblasti formuláře. Třídu objektů factory oblasti formuláře zodpovídá za vytvoření nové instance třídy oblasti formuláře.  
  
 Tato třída rozšířením můžete najít **Factory oblasti formuláře** oblast.  
  
 **Nové oblasti formuláře aplikace Outlook** průvodce přidá atributy a třídy zpráv, které zobrazení oblasti formuláře tuto třídu, která zadejte interní název oblasti formuláře. Tyto atributy lze upravit ručně po přidání souboru do projektu.  
  
 Většina třídu objektů factory oblasti formuláře je implementovaná v souboru návrháře oblasti formuláře. Ale `FormRegionInitializing` obslužné rutiny události vystavený v souboru kódu oblasti formuláře. Tuto obslužnou rutinu události můžete použít k určení, zda má aplikace Outlook zobrazit oblasti formuláře. Další informace najdete v tématu [zpracování událostí oblasti formuláře](#HandlingFormRegionEvents).  
  
###  <a name="AddingExistingFormRegion"></a> Přidejte existující oblasti formuláře do projektu  
 Pokud máte oblasti formuláře aplikace Outlook, který jste použili v jiném projektu aplikace Outlook, můžete opakovaně použít jej v aktuálním projektu doplňku VSTO pro Outlook pomocí **přidat existující položku** dialogové okno.  
  
 Existující oblasti formuláře musí mít souboru kódu (*VB* nebo *.cs*); nelze přidat úložiště formuláře aplikace Outlook (*.ofs*) souborů pomocí **přidat existující položku** dialogové okno. Můžete však vytvořit novou oblasti formuláře importováním souboru úložiště formuláře aplikace Outlook. Další informace najdete v tématu [postupy: přidání oblasti formuláře do projektu doplněk aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md).  
  
##  <a name="UsingFormRegionDesigner"></a> Použití návrháře oblasti formuláře  
 Návrhář oblasti formuláře umožňuje návrh rozložení a vzhled oblasti formuláře. Přetáhněte spravované ovládací prvky na plochu návrháře, dvakrát klikněte na ovládací prvky pro otevření obslužné rutiny událostí a v nastavit vlastnosti **vlastnosti** okno.  
  
> [!NOTE]  
>  Můžete najít vlastnosti, které ovlivní způsob, jakým oblasti formuláře se zobrazí v aplikaci Outlook pod **Manifest** uzlu **vlastnosti** okno.  
  
 Návrhář oblasti formuláře je k dispozici pouze v případě, že vyberete **návrhu nové oblasti formuláře** v **vyberte způsob vytvoření oblasti formuláře** stránky **nové oblasti formuláře aplikace Outlook** Průvodce.  
  
 Existují tři způsoby, jak otevřít Návrhář oblasti formuláře:  
  
-   V **Průzkumníku**, poklikejte na soubor kód oblasti formuláře.  
  
-   V **Průzkumníku řešení**, klikněte pravým tlačítkem na soubor kód oblasti formuláře a potom klikněte na **Návrhář zobrazení**.  
  
-   V **Průzkumníku řešení**, vyberte soubor kód oblasti formuláře a pak klikněte na **zobrazení** nabídky, klikněte na tlačítko **Návrhář**.  
  
 Návrhář podporuje oblasti formuláře pouze spravovaných ovládacích prvků. Nelze přidat nativní ovládací prvky aplikace Outlook.  
  
##  <a name="UsingFormRegionDesignedOutlook"></a> Import oblasti formuláře navržené v aplikaci Outlook  
 Při návrhu v aplikaci Outlook, můžete přidat nativní ovládací prvky aplikace Outlook k oblasti formuláře. Nativní ovládací prvky aplikace Outlook umožňují vázat na data Outlooku v době návrhu. Spravované ovládací prvky přidat nebo změnit návrh oblasti formuláře však nelze pak použít Návrháře oblasti formuláře.  
  
 Oblasti formuláře do projektu doplňku VSTO v Outlooku můžete importovat pomocí **nové oblasti formuláře aplikace Outlook** průvodce. Na **vyberte způsob vytvoření oblasti formuláře** vyberte **importovat soubor úložiště formuláře aplikace Outlook (.ofs)**. Potom můžete vyhledat umístění souboru úložiště formuláře aplikace Outlook (*.ofs*) souboru. (Outlook uloží oblasti formuláře jako *.ofs* soubory.)  
  
 **Nové oblasti formuláře aplikace Outlook** Průvodce kopií *.ofs* soubor do adresáře projektu a přidá odkazy na ovládací prvek návrháře soubor oblasti formuláře. Potom může zpracovávat události ovládacího prvku v souboru kódu oblasti formuláře.  
  
 Zpracování událostí v projektu jazyka Visual Basic, vyberte ze seznamu Metoda název v horní části editoru kódu událost.  
  
 Zpracování událostí v projektu C#, se přihlásit k odběru události ovládacího prvku v <xref:Microsoft.Office.Tools.Outlook.FormRegionControl.FormRegionShowing> metoda. Další informace najdete v tématu [postupy: přihlášení a odhlášení odběru událostí &#40;C&#35; Průvodce programováním&#41;](/dotnet/csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events).  
  
 Můžete změnit vlastnosti oblasti formuláře v `InitializeManifest` metoda třídu objektů factory oblasti formuláře.  
  
> [!NOTE]  
>  Import oblasti formuláře, je třeba pracovat v projektu s cílem stejnou verzi aplikace Outlook, který jste nainstalovali na vývojovém počítači. Například pokud máte nainstalovanou aplikaci Outlook 2010, import formuláře oblast bude pouze pracovní v projektu byla vytvořena pomocí **doplněk aplikace Outlook 2010** šablona projektu.  
  
### <a name="update-an-imported-form-regions-design"></a>Aktualizovat oblast importované formuláře návrhu  
 Můžete přidat, odebrat ani změnit ovládacích prvků na oblasti formuláře. Než to uděláte, zálohujte žádný kód, který jste přidali do souboru kódu oblasti formuláře. Potom otevřete *.ofs* souboru v aplikaci Outlook, úpravě oblasti formuláře a potom uložte změny. Použití **nové oblasti formuláře aplikace Outlook** Průvodce pro import upravenou *.ofs* souboru. Potom můžete vložit kódu do nového souboru kód oblasti formuláře.  
  
##  <a name="AddingCustomCode"></a> Přidat vlastní kód do oblasti formuláře  
 <xref:Microsoft.Office.Tools.Outlook> Obor názvů umožňuje přístup k tříd, které představují oblasti formuláře, se zobrazí oblasti formuláře položku aplikace Outlook a další užitečné položky. **Oblasti formuláře aplikace Outlook** položky automaticky přidá odkaz na toto sestavení v projektu a vloží odpovídající **pomocí** nebo **importy** příkaz v horní části soubor kód oblasti formuláře.  
  
 Můžete použít tříd, metod a vlastností v `Microsoft.Office.Interop.Outlook` oboru názvů k většině v aplikaci Outlook programovacích úloh. Další informace o modelu objektů aplikace Outlook najdete v tématu [přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md). Příklady typických úkolů, které tvoří použít modelu objektů aplikace Outlook, najdete v části [řešení pro aplikaci Outlook](../vsto/outlook-solutions.md).  
  
###  <a name="HandlingFormRegionEvents"></a> Zpracování událostí oblasti formuláře  
 **Oblasti formuláře aplikace Outlook** následující obslužné rutiny událostí tři položky automaticky přidá do souboru kódu oblasti formuláře.  
  
|Událost|Popis|  
|-----------|-----------------|  
|FormRegionInitializing|Nastane před inicializací oblasti formuláře. Můžete zkontrolovat podmínky v této obslužné rutiny události k určení, zda má aplikace Outlook zobrazit oblasti formuláře. Další informace najdete v tématu [postupy: zabránění Outlook ze zobrazení oblasti formuláře](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md).|  
|FormRegionShowing|Vyvolá se po vytvoření instance oblasti formuláře, ale před zobrazením této oblasti.|  
|FormRegionClosed|Vyvolá se před uzavřením oblasti formuláře.|  
  
##  <a name="Building"></a> Sestavení projektu  
 Při sestavování projektu doplňku VSTO pro Outlook, která obsahuje oblasti formuláře, Visual Studio přidá do registru následující informace:  
  
-   Klíč pro každou třídu zpráv, který je přidružen jeden nebo více oblastí formulářů.  
  
-   Záznam pro každou oblast formuláře a přidružené hodnoty, který představuje název doplňku VSTO v Outlooku.  
  
 Outlook používá tyto informace načíst oblasti formuláře.  
  
##  <a name="Debugging"></a> Ladění oblasti formuláře  
 Můžete ladit aplikace Outlook VSTO doplněk obsahující oblasti formuláře stejně, jako by ladění dalších [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projekty. Při prvním spuštění [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ladicí program, Visual Studio automaticky spustí aplikaci Outlook.  
  
 K zobrazení oblasti formuláře, je nutné otevřít příslušnou položku aplikace Outlook. Například pokud oblast sousedících formuláře se připojí k dolnímu okraji položku e-mailu, otevřete položku e-mailu.  
  
##  <a name="Deploying"></a> Nasazení oblasti formuláře  
 Oblasti formuláře se nasazují automaticky pomocí přidružené Add-in VSTO pro Outlook. Proto nemáte žádné zvláštní úkoly nasazení oblasti formuláře. Další informace o nasazení doplňků VSTO najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Pokyny pro vytváření oblastí formulářů aplikace Outlook](../vsto/guidelines-for-creating-outlook-form-regions.md)|Poskytuje informace, které vám může pomoct optimalizovat vaší oblasti formuláře a nedocházelo k problémům.|  
|[Postupy: přidání oblasti formuláře do projektu doplněk aplikace Outlook](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)|Ukazuje, jak vytvořit oblasti formuláře rozšíření pomocí formuláře aplikace Microsoft Office Outlook standardními nebo vlastními **nové oblasti formuláře aplikace Outlook** průvodce.|  
|[Přidružení oblasti formuláře k třídě zpráv aplikace Outlook](../vsto/associating-a-form-region-with-an-outlook-message-class.md)|Vysvětluje, jak určit, které aplikace Microsoft Office Outlook položky zobrazení oblasti formuláře ve přidružení oblasti formuláře k třídě zpráv každé položky.|  
|[Návod: Návrh oblasti formuláře aplikace Outlook](../vsto/walkthrough-designing-an-outlook-form-region.md)|Ukazuje, jak navrhnout vlastní formulář oblasti, která se zobrazí jako nová stránka v okně Inspector kontaktní položky.|  
|[Návod: Importujte oblasti formuláře navržené v aplikaci Outlook](../vsto/walkthrough-importing-a-form-region-that-is-designed-in-outlook.md)|Ukazuje, jak návrh oblasti formuláře v aplikaci Microsoft Office Outlook a pak import oblasti formuláře do projektu doplňku VSTO pro Outlook pomocí **nové oblasti formuláře aplikace Outlook** průvodce.|  
|[Přístup k oblasti formuláře za běhu](../vsto/accessing-a-form-region-at-run-time.md)|Popisuje, jak napsat kód pro zobrazení, skrytí nebo úprava ovládacích prvků na oblasti formuláře a povolit uživatelům spustit kód z jiných oblastí ve vašem projektu pomocí `Globals` třídy.|  
|[Postupy: zabránění zobrazení oblasti formuláře aplikace Outlook](../vsto/how-to-prevent-outlook-from-displaying-a-form-region.md)|Ukazuje, jak zabránit zobrazení oblasti formuláře pro konkrétní položku aplikace Microsoft Office Outlook.|  
|Ukazuje, jak získat přístup k položce Outlook, ve kterém se zobrazí oblasti formuláře.|  
|[Vlastní akce v oblastí formulářů aplikace Outlook](../vsto/custom-actions-in-outlook-form-regions.md)|Popisuje, jak povolit uživatelům reagovat na položku aplikace Outlook.|  
  
