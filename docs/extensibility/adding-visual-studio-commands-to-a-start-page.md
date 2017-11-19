---
title: "Přidání příkazů sady Visual Studio na úvodní stránku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- start page commands
- vs:VSCommands
ms.assetid: a8e2765c-cfb5-47b5-a414-6e48b434e0c2
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 973e0cfbceb6cbf67c5bc11cdde370607334809a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="adding-visual-studio-commands-to-a-start-page"></a>Přidání příkazů sady Visual Studio na úvodní stránky
Když vytvoříte vlastní úvodní stránky, můžete do něj může přidat příkazy sady Visual Studio. Tento dokument popisuje různé způsoby, jak vytvořit vazbu příkazy sady Visual Studio na objekty XAML na úvodní stránce.  
  
 Další informace o příkazech v jazyce XAML najdete v tématu [tvorba příkazů – přehled](/dotnet/framework/wpf/advanced/commanding-overview)  
  
## <a name="adding-commands-from-the-command-well"></a>Přidání příkazů z příkazu dobře  
 Úvodní stránky vytvořené v [vytváření vlastní – úvodní stránka](../extensibility/creating-a-custom-start-page.md) přidat <xref:Microsoft.VisualStudio.PlatformUI?displayProperty=fullName> a <xref:Microsoft.VisualStudio.Shell?displayProperty=fullName> obory názvů, následujícím způsobem.  
  
```  
xmlns:vs="clr-namespace:Microsoft.VisualStudio.PlatformUI;assembly=Microsoft.VisualStudio.Shell.14.0"  
xmlns:vsfx="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.14.0"  
```  
  
 Přidejte jiný obor názvů pro Microsoft.VisualStudio.Shell ze sestavení Microsoft.VisualStudio.Shell.Immutable.11.0.dll. (Možná bude muset přidat odkaz na toto sestavení v projektu.)  
  
```xml  
xmlns:vscom="clr-namespace:Microsoft.VisualStudio.Shell;assembly=Microsoft.VisualStudio.Shell.Immutable.11.0"  
```  
  
 Můžete použít `vscom:` alias pro vazbu příkazy sady Visual Studio XAML ovládací prvky na stránce nastavením <xref:System.Windows.Controls.Primitives.ButtonBase.Command%2A> vlastnost ovládacího prvku na `vscom:VSCommands.ExecuteCommand`. Pak můžete nastavit <xref:System.Windows.Controls.Primitives.ButtonBase.CommandParameter%2A> vlastnost na název provedení příkazu, jak je znázorněno v následujícím příkladu.  
  
```xml  
<Button Name="btnNewProj" Content="New Project"   
    Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
    CommandParameter="File.NewProject" >  
</Button>  
```  
  
> [!NOTE]
>  `x:` Alias, který odkazuje schématu XAML, není třeba na začátku všechny příkazy.  
  
 Můžete nastavit hodnotu `Command` vlastnost na libovolný příkaz, který je přístupný z **příkaz** okno. Seznam dostupných příkazů najdete v tématu [aliasy příkazů Visual Studio](../ide/reference/visual-studio-command-aliases.md).  
  
 Pokud příkaz pro přidání vyžaduje další parametr, můžete ho přidat na hodnotu `CommandParameter` vlastnost. Samostatné parametry z příkazů pomocí mezer, jak je znázorněno v následujícím příkladu.  
  
```xml  
<Button Content="Web Search"   
        Command="{x:Static vscom:VSCommands.ExecuteCommand}"  
        CommandParameter="View.WebBrowser www.bing.com" />  
```  
  
### <a name="calling-extensions-from-the-command-well"></a>Volání metody rozšíření z příkazu dobře  
 Příkazy můžete volat z registrovaných VSPackages pomocí stejné syntaxi, která se používá k volání další příkazy sady Visual Studio. Například, pokud přidá nainstalované VSPackage **domovskou stránku** příkaz **zobrazení** nabídky, tento příkaz můžete volat nastavením `CommandParameter` k `View.HomePage`.  
  
> [!NOTE]
>  Když zavoláte příkaz, který je přidružen VSPackage, musí balíček načíst při vyvolání příkazu.  
  
## <a name="adding-commands-from-assemblies"></a>Přidání příkazů ze sestavení  
 Příkaz volat z sestavení nebo na přístupový kód ve VSPackage, který není spojen s příkazu nabídky, musíte vytvořit alias pro sestavení a pak zavolají alias.  
  
#### <a name="to-call-a-command-from-an-assembly"></a>Volání příkazu ze sestavení  
  
1.  Ve vašem řešení přidáte odkaz na sestavení.  
  
2.  V horní části souboru StartPage.xaml přidáte direktivu obor názvů pro sestavení, jak je znázorněno v následujícím příkladu.  
  
    ```xml  
    xmlns:vsc="clr-namespace:WebUserControl;assembly=WebUserControl"  
    ```  
  
3.  Vyvolat příkaz nastavením `Command` vlastnost objektu XAML, jak je znázorněno v následujícím příkladu.  
  
     XAML  
  
    ```  
    <vs:Button Text="Hide me" Command="{x:Static vsc:HideControl}" .../>  
    ```  
  
> [!NOTE]
>  Vaše sestavení zkopírujte a vložte jej do... \\ *Instalační složka nástroje visual Studio*\Common7\IDE\PrivateAssemblies\ a ujistěte se, je načtena, než je volána.  
  
## <a name="adding-commands-with-the-dte-object"></a>Přidání příkazů s objektem DTE  
 Objekt DTE můžete přistupovat z spuštění stránky, jak v značek a kódu.  
  
 V kódu, můžete k němu přístup pomocí [vazby – rozšíření značek](/dotnet/framework/wpf/advanced/binding-markup-extension) syntaxi pro volání <xref:EnvDTE.DTE> objektu. Tento postup můžete použít k vytvoření vazby jednoduché vlastnosti, jako jsou ty, které vrací kolekce, ale nemůže vytvořit vazbu k metody nebo služby. Následující příklad ukazuje <xref:System.Windows.Controls.TextBlock> řízení, která se sváže s <xref:EnvDTE._DTE.Name%2A> vlastnost a <xref:System.Windows.Controls.ListBox> ovládací prvek, který se zobrazí <xref:EnvDTE.Window.Caption%2A> vlastnosti kolekce, který je vrácen <xref:EnvDTE._DTE.Windows%2A> vlastnost.  
  
```xml  
<TextBlock Text="{Binding Path=DTE.Name}" FontSize="12" HorizontalAlignment="Center"/>  
<ListBox ItemsSource="{Binding Path=DTE.Windows}">  
    <ListBox.ItemTemplate>  
        <DataTemplate>  
            <TextBlock Text="{Binding Path=Caption}"/>  
        </DataTemplate>  
    </ListBox.ItemTemplate>  
</ListBox  
```  
  
 Příklad, naleznete v části [návod: ukládání nastavení uživatele na stránce Start](../extensibility/walkthrough-saving-user-settings-on-a-start-page.md).  
  
## <a name="see-also"></a>Viz také  
 [Přidání uživatelského ovládacího prvku do úvodní stránky](../extensibility/adding-user-control-to-the-start-page.md)