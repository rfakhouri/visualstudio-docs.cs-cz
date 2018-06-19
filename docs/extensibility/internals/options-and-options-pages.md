---
title: Možnosti a možnosti stránky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Tools Options pages [Visual Studio SDK], managed package framework support
- managed package framework, Tools Options pages support
- support, Tools Options pages
- Tools Options pages [Visual Studio SDK], layouts
- Tools Options pages [Visual Studio SDK], attributes
ms.assetid: e6c0e636-5ec3-450e-b395-fc4bb9d75918
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d85b900779a5df8af077b292b2e2f70b0592e35c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31132928"
---
# <a name="options-and-options-pages"></a>Možnosti a možnosti stránky
Kliknutím na tlačítko **možnosti** na **nástroje** otevře se nabídka **možnosti** dialogové okno. Možnosti v tomto dialogovém se souhrnně označují jako možnosti stránky. V navigačním podokně ovládacího prvku strom zahrnuje možnosti kategorií a každou kategorii má možnosti stránky. Když vyberete na stránce, v pravém podokně zobrazí jeho možnosti. Tyto stránek umožňují změnit hodnoty možnosti, které určují stav VSPackage.  
  
## <a name="support-for-options-pages"></a>Podporu pro možnosti stránky  
 <xref:Microsoft.VisualStudio.Shell.Package> Třída poskytuje podporu pro vytváření možnosti stránky a možnosti kategorií. <xref:Microsoft.VisualStudio.Shell.DialogPage> Třída implementuje stránku možnosti.  
  
 Výchozí implementaci <xref:Microsoft.VisualStudio.Shell.DialogPage> nabízí jeho veřejné vlastnosti uživatele v obecné mřížku vlastností. Toto chování můžete přizpůsobit přepsáním různé metody na stránce a vytvořte vlastní možnosti stránku, která má své vlastní uživatelské rozhraní (UI). Další informace najdete v tématu [vytváření stránku možnosti](../../extensibility/creating-an-options-page.md).  
  
 <xref:Microsoft.VisualStudio.Shell.DialogPage> Třída implementuje <xref:Microsoft.VisualStudio.Shell.IProfileManager>, který poskytuje trvalosti pro možnosti stránky a také pro nastavení uživatele. Výchozí implementace <xref:Microsoft.VisualStudio.Shell.IProfileManager.LoadSettingsFromStorage%2A> a <xref:Microsoft.VisualStudio.Shell.IProfileManager.SaveSettingsToStorage%2A> metody zachovat změny vlastností do uživatele oddíl registru, pokud vlastnost převést do a z řetězce.  
  
## <a name="options-page-registry-path"></a>Cesta v registru možnosti stránky  
 Ve výchozím nastavení, je určen vlastností spravuje stránku možnosti cestu registru tím, že zkombinujete <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>, word DialogPage a název typu třídy stránky možnosti. Například třída možností stránky mohou být definovány takto.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#1](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_1.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#1](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_1.vb)]  
  
 Pokud <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A> je HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp, pak jsou podklíče HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp\DialogPage\ dvojice název a hodnota vlastnosti Company.OptionsPage.OptionsPageGeneral.  
  
 Cestu registru možnosti stránky je dáno kombinování <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, slovo, ToolsOptionsPages a možnosti stránky kategorie a název. Například, pokud na stránce Možnosti vlastní má kategorií, My možnost stránek a <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A> je HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp, pak na stránce Možnosti má klíč registru, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ Možnost Pages\Custom VisualStudio\8.0Exp\ToolsOptionsPages\My.  
  
## <a name="toolsoptions-page-attributes-and-layout"></a>Atributy stránky nástroje/Možnosti a rozložení  
 <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> Atribut určuje vlastní možnosti stránek seskupení do kategorií v navigačním stromu **možnosti** dialogové okno. <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> Atribut přidruží stránku možnosti VSPackage, která poskytuje rozhraní. Předpokládejme následující fragment kódu:  
  
 [!code-csharp[VSSDKSupportForOptionsPages#2](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_2.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#2](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_2.vb)]  
  
 To deklaruje, že MyPackage poskytuje dvě možnosti stránky, OptionsPageGeneral a OptionsPageCustom. V **možnosti** dialogové okno, zobrazí se v obou možnosti stránky **Moje stránky možnost** kategorie jako **Obecné** a **vlastní**, v uvedeném pořadí.  
  
## <a name="option-attributes-and-layout"></a>Možnost atributy a rozložení  
 Uživatelské rozhraní (UI), které poskytuje stránce určuje vzhled možnosti na stránce vlastní možnosti. Rozložení, označování a popis možnosti na stránce Obecné možnosti jsou určeny následující atributy:  
  
-   <xref:System.ComponentModel.CategoryAttribute> Určuje kategorii možnost.  
  
-   <xref:System.ComponentModel.DisplayNameAttribute> Určuje zobrazovaný název možnosti.  
  
-   <xref:System.ComponentModel.DescriptionAttribute> Určuje popis možnosti.  
  
    > [!NOTE]
    >  Ekvivalentní atributy, SRCategory, LocDisplayName a SRDescription, používat prostředky řetězce pro lokalizaci a jsou definovány v [spravovaný projekt ukázka](http://go.microsoft.com/fwlink/?LinkId=122774).  
  
 Předpokládejme následující fragment kódu:  
  
 [!code-csharp[VSSDKSupportForOptionsPages#3](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_3.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#3](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_3.vb)]  
  
 OptionInteger možnost se zobrazí na stránce možnosti jako **celé číslo možnost** v **Moje možnosti** kategorie. Pokud je vybrána možnost, popis, **Moje celé číslo možnost**, zobrazí se v poli Popis.  
  
## <a name="accessing-options-pages-from-another-vspackage"></a>Přístup k možnosti stránky z jiného VSPackage  
 VSPackage, který je hostitelem a spravuje stránku možnosti můžete programově přístupná z jiné VSPackage pomocí modelu automatizace. Například v následujícím kódu je VSPackage registrován jako hostování stránku možnost.  
  
 [!code-csharp[VSSDKSupportForOptionsPages#4](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_4.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#4](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_4.vb)]  
  
 Následující fragment kódu získá hodnotu OptionInteger z MyOptionPage:  
  
 [!code-csharp[VSSDKSupportForOptionsPages#5](../../extensibility/internals/codesnippet/CSharp/options-and-options-pages_5.cs)]
 [!code-vb[VSSDKSupportForOptionsPages#5](../../extensibility/internals/codesnippet/VisualBasic/options-and-options-pages_5.vb)]  
  
 Když <xref:Microsoft.VisualStudio.Shell.ProvideOptionPageAttribute> atribut zaregistruje stránku možnosti, stránky je zaregistrovaný pod klíče Pokud AutomationProperties `SupportsAutomation` argument atributu je `true`. Automatizace prozkoumá této položky registru najít přidružené VSPackage a automatizace pak vlastnost přistupuje prostřednictvím hostované stránce Možnosti, v takovém případě stránku mřížky.  
  
 Cestu registru vlastnosti automatizace je dáno kombinování <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, slovo, AutomationProperties a možnosti stránky kategorie a název. Například, pokud na stránce Možnosti má Moje kategorie kategorie, název stránku mřížky a <xref:Microsoft.VisualStudio.Shell.Package.ApplicationRegistryRoot%2A>, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp, pak vlastnost automatizace má klíč registru, HKEY_LOCAL_MACHINE\SOFTWARE\ Microsoft\VisualStudio\8.0Exp\AutomationProperties\My Category\My mřížky stránky.  
  
> [!NOTE]
>  Kanonický název stránky mřížky Moje Category.My, je hodnota podklíče název tohoto klíče.