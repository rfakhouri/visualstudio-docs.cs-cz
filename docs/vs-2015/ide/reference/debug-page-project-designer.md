---
title: Stránka ladění, Návrhář projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vb.ProjectPropertiesDebug
helpviewer_keywords:
- Project Designer, Debug page
- Debug page in Project Designer
ms.assetid: ef11eae9-df96-4e20-aabd-2678ba317140
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 25ffe4f9280dfbb0b3146ebf8b3dd7b62e908814
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63441420"
---
# <a name="debug-page-project-designer"></a>Stránka Ladění, návrhář projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

> [!WARNING]
> Toto téma se nevztahuje na aplikace Windows Store. Zobrazit [spustíte relaci ladění (VB, C#, C++ a XAML)](../../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md) Windows Dev Center.  
  
 Použití **ladění** stránku **Návrháře projektu** můžete nastavit vlastnosti pro ladění chování v projektu jazyka Visual Basic nebo C#.  
  
 Pro přístup **ladění** stránky, vyberte uzel projektu v **Průzkumníka řešení**. Na **projektu** nabídce zvolte _ProjectName_**vlastnosti**. Když **Návrháře projektu** se zobrazí, klikněte na tlačítko **ladění** kartu.  
  
## <a name="configuration-and-platform"></a>Konfigurace a platforma  
 Tyto možnosti umožňují vybrat konfigurace a platformy k zobrazení a úpravě.  
  
 **Konfigurace**  
 Určuje které nastavení konfigurace má být zobrazeno nebo upraveno. Toto nastavení může být **ladění** (výchozí), **vydání**, nebo **všechny konfigurace**. Další informace najdete v tématu [konfigurace ladění a verzí projektu](http://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e).  
  
 **Platforma**  
 Určuje které nastavení platformy má být zobrazeno nebo upraveno. Může zahrnovat volby **jakýkoli procesor** (výchozí), **x64**, a **x86**. Další informace najdete v tématu [konfigurace ladění a verzí projektu](http://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e).  
  
## <a name="start-action"></a>Spustit akci  
 **Zahájení** označuje položku, která se spustí při ladění aplikace: projekt, vlastní program, adresu URL nebo žádnou akci. Ve výchozím nastavení je tato možnost nastavená na **spustit projekt**. **Spustit akci** nastavení **ladění** stránky určuje hodnotu `StartAction` vlastnost.  
  
 **Spustit projekt**  
 Tato možnost slouží k určení, že spustitelný soubor (pro projekty aplikací pro Windows a Konzolová aplikace) by měl být spuštěn při ladění aplikace. Ve výchozím nastavení je vybraná tato možnost.  
  
 **spustit externí program**  
 Tato možnost slouží k určení, že konkrétní program má být spuštěn při ladění aplikace.  
  
 **Spustit prohlížeč s adresou URL**  
 Tato možnost slouží k určení, že určité adresy URL by měl mít přístup při ladění aplikace.  
  
## <a name="start-options"></a>Možnosti spuštění  
 **Argumenty příkazového řádku**  
 Do tohoto textového pole zadejte argumenty příkazového řádku pro ladění.  
  
 **Pracovní adresář**  
 Do tohoto textového pole zadejte adresář, ze které bude projekt spustit. Nebo klikněte na tlačítko Procházet (**...** ) Chcete-li vybrat adresář.  
  
 **Použití vzdáleného počítače**  
 Chcete-li ladit aplikaci ze vzdáleného počítače, zaškrtněte toto políčko a zadejte cestu ke vzdálenému počítači v textovém poli.  
  
## <a name="enable-debuggers"></a>Povolit ladicí programy  
 **Povolit ladění nespravovaného kódu**  
 Tato možnost určuje, zda je podporováno ladění nativního kódu. Toto políčko zaškrtněte, pokud jsou objekty COM volání nebo spustit vlastní program napsány v nativním kódu, která volá váš projekt a musí ladění nativního kódu. Zrušte zaškrtnutí tohoto políčka Zakázat ladění nespravovaného kódu. Toto políčko je ve výchozím nastavení zaškrtnuté.  
  
 **Povolit ladění SQL serveru**  
 Zaškrtněte nebo zrušte zaškrtnutí políčka Povolit nebo zakázat ladění procedur SQL z aplikace Visual Basic. Toto políčko je ve výchozím nastavení zaškrtnuté.  
  
 **Povolit hostující proces sady Visual Studio**  
 Zaškrtněte toto políčko, aby hostující proces sady Visual Studio. Toto zaškrtávací políčko je ve výchozím nastavení zaškrtnuto. Další informace najdete v tématu [proces hostování (vshost.exe)](../../ide/hosting-process-vshost-exe.md).  
  
 Chcete-li ladit v zóně zabezpečení, musíte tuto volbu Povolit a **Ladit tuto aplikaci s vybranou sadou oprávnění** v [rozšířené zabezpečení dialogové okno nastavení](../../ide/reference/advanced-security-settings-dialog-box.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladění v sadě Visual Studio](../../debugger/debugging-in-visual-studio.md)   
 [Nastavení projektu pro jazyk C# konfiguraci ladění](../../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Konfigurace ladění projektu v jazyce Visual Basic](../../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Správa vlastností ladění](http://msdn.microsoft.com/92474d16-e7fe-4fac-9287-6bd6b3a7eb68)   
 [Postupy: Ladění aplikace ClickOnce s omezenými oprávněními](../../deployment/how-to-debug-a-clickonce-application-with-restricted-permissions.md)   
 [Postupy: Vytvoření a úprava konfigurací](../../ide/how-to-create-and-edit-configurations.md)
