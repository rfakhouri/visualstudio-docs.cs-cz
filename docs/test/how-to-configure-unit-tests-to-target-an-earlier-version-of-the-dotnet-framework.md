---
title: Konfigurace testů jednotek pro cílení na dřívější verzi rozhraní .NET Framework v sadě Visual Studio | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
author: gewarren
ms.openlocfilehash: 2c0a34e3a046b840024e7dbfb4b7761fcaec5cfa
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-configure-unit-tests-to-target-an-earlier-version-of-the-net-framework"></a>Postupy: Konfigurace testů jednotek pro cílení na dřívější verzi rozhraní .NET Framework

Když vytvoříte projekt testů v sadě Microsoft Visual Studio, je jako cíl, ve výchozím nastavení nejnovější verzi rozhraní .NET Framework. Kromě toho pokud provádíte upgrade projektů testů z předchozích verzí sady Visual Studio, se upgradují na nejnovější verzi rozhraní .NET Framework. Úpravou vlastností projektu, můžete explicitně znovu vybrat projektu na dřívější verze rozhraní .NET Framework.

Můžete vytvořit jednotku projektů testů, které cílí určité verze rozhraní .NET Framework. Cílová verze musí být 3.5 nebo novější a nelze na verzi klienta. Visual Studio umožňuje následující základní podporu pro testování částí, které cílí určité verze:

- Můžete vytvořit projektů testování částí a cílení na konkrétní verzi rozhraní .NET Framework.

- Můžete spustit testy jednotek cílených na konkrétní verzi rozhraní .NET Framework ze sady Visual Studio na místním počítači.

- Testy jednotek můžete spustit z příkazového řádku pomocí MSTest.exe cílených na konkrétní verzi rozhraní .NET Framework.

- Spouštění testování částí v sestavení agenta jako součást sestavení.

**Testování aplikací pro SharePoint**

Možnosti uvedené výše také umožňují zápisu testy částí a testy integrace aplikací služby SharePoint pomocí sady Visual Studio. Další informace o vývoji aplikací služby SharePoint pomocí sady Visual Studio najdete v tématu [vytvořit řešení služby SharePoint](/office-dev/office-dev/create-sharepoint-solutions), [sestavování a ladění řešení služby SharePoint](/office-dev/office-dev/building-and-debugging-sharepoint-solutions) a [ověření a ladění kódu pro SharePoint](/office-dev/office-dev/verifying-and-debugging-sharepoint-code).

**Omezení**

Když znovu cíle testovací projekty, aby používaly starší verze rozhraní .NET Framework, platí následující omezení:

- V rozhraní .NET Framework 3.5 je podporováno cílení na více verzí pro testovací projekty, které obsahují pouze jednotky testy. Rozhraní .NET Framework 3.5 nepodporuje žádné jiné testovací typu, například programových testů uživatelského rozhraní nebo zatížení. Cílení znovu je blokován pro test jiného typu než testování částí.

- Spuštění testů, které jsou zaměřeny na dřívější verzi rozhraní .NET Framework je podporován pouze ve výchozím nastavení adaptéru hostitele. Nepodporuje se v adaptéru hostitele technologie ASP.NET. Aplikace ASP.NET, které mají na spouštění v kontextu vývojový Server ASP.NET musí být kompatibilní s aktuální verze rozhraní .NET Framework.

- Podpora kolekce dat je zakázána, když spustíte testy, které podporují cílení na více verzí rozhraní .NET Framework 3.5. Pokrytí kódu můžete spustit pomocí příkazového řádku nástroje sady Visual Studio.

- Na vzdáleném počítači nelze spustit testy jednotek, které používají rozhraní .NET Framework 3.5.

- Cílem nemůže testů jednotek pro starší verze klienta architektury.

## <a name="re-targeting-to-a-specific-version-of-the-net-framework-for-visual-basic-unit-test-projects"></a>Znovu cílení na konkrétní verzi rozhraní .NET Framework pro projektů testování částí Visual Basic

1.  Vytvoření nového projektu testování částí jazyka Visual Basic. Na **soubor** nabídce zvolte **nový** a potom zvolte **projektu**.

     **Nový projekt** se zobrazí dialogové okno.

2.  V části **nainstalovaných šablonách**, rozbalte položku **jazyka Visual Basic**. Vyberte **Test** a pak vyberte **testovacího projektu** šablony.

3.  V **název** textového pole, zadejte název v jazyce Visual Basic testování projektu a potom zvolte **OK**.

4.  V Průzkumníku řešení, zvolte **vlastnosti** z místní nabídky nového testovacího projektu Visual Basic.

     Zobrazí se vlastnosti testovacího projektu Visual Basic.

5.  Na **zkompilovat** , zvolte **Upřesnit možnosti kompilace** jak je znázorněno na následujícím obrázku.

     ![Rozšířené možnosti kompilace](../test/media/howtoconfigureunittest35frameworka.png "HowToConfigureUnitTest35FrameworkA")

6.  Použití **cílové rozhraní (všechny konfigurace)** rozevíracího seznamu můžete změnit cílové rozhraní k **rozhraní .NET Framework 3.5** nebo novější verze, jak je znázorněno na následujícím obrázku popisku B. Neměla by být zadána jako verze klienta.

     ![Cílový framework rozevírací&#45;dolů seznamu](../test/media/howtoconfigureunitest35frameworkstepb.png "HowToConfigureUniTest35FrameworkStepB")

## <a name="re-targeting-to-a-specific-version-of-the-net-framework-for-visual-c-unit-test-projects"></a>Znovu cílení na konkrétní verzi rozhraní .NET Framework pro Visual C# projektů testování částí

1.  Vytvořte nový projekt testování částí Visual C#. Na **soubor** nabídce zvolte **nový** a potom zvolte **projektu**.

     **Nový projekt** se zobrazí dialogové okno.

2.  V části **nainstalovaných šablonách**, rozbalte položku **Visual C#**. Vyberte **Test** a pak vyberte **testovacího projektu** šablony.

3.  V **název** textového pole, zadejte název pro vaše Visual C# testování projektu a potom zvolte **OK**.

4.  V Průzkumníku řešení, zvolte **vlastnosti** z místní nabídky Nový projekt test Visual C#.

     Zobrazí se vlastnosti testovacího projektu Visual C#.

5.  Na **aplikace** , zvolte **cílové rozhraní**. V rozevíracím seznamu vyberte **rozhraní .NET Framework 3.5** nebo novější, jak je znázorněno na následujícím obrázku. Neměla by být zadána jako verze klienta.

     ![Cílový framework rozevírací&#45;dolů seznamu](../test/media/howtoconfigureunittest35frameworkcsharp.png "HowToConfigureUnitTest35FrameworkCSharp")

## <a name="re-targeting-to-a-specific-version-of-the-net-framework-for-ccli-unit-test-projects"></a>Znovu cílení na konkrétní verzi rozhraní .NET Framework pro C + +/ CLI projektů testování částí

1.  Vytvořte nový projekt testování částí C++. Na **soubor** nabídce vyberte možnost **nový** a pak klikněte na **projektu**.

     **Nový projekt** se zobrazí dialogové okno.

    > [!WARNING]
    > K sestavení C + +/ CLI testů jednotek aplikací pro předchozí verze rozhraní .NET Framework pro Visual C++, je nutné použít odpovídající verzi sady Visual Studio. Například pro rozhraní .NET Framework 3.5, nainstalujte Visual Studio 2008 a Visual Studio 2008 Service Pack 1.

2.  V části **nainstalovaných šablonách**, rozbalte položku **Visual C ++**. Vyberte **Test** a pak vyberte **testovacího projektu** šablony.

3.  V **název** textového pole, zadejte název pro Visual C++ testování projektu a pak klikněte na tlačítko **OK**.

4.  V Průzkumníku řešení, zvolte **uvolnit projekt** z nového testovacího projektu Visual C++.

5.  V Průzkumníku řešení, zvolte odpojen testovacího projektu Visual C++ a pak **upravit \<název projektu > VCXPROJ**.

     VCXPROJ soubor se otevře v editoru.

6.  Nastavte `TargetFrameworkVersion` verze 3.5 nebo novější verze v `PropertyGroup` s názvem bez přípony `"Globals"`. Neměla by být zadána jako verze klienta:

    ```xml
    <PropertyGroup Label="Globals">
        <TargetName>DefaultTest</TargetName>
        <ProjectTypes>{3AC096D0-A1C2-E12C-1390-A8335801FDAB};{8BC9CEB8-8B4A-11D0-8D11-00A0C91BC942}</ProjectTypes>
        <ProjectGUID>{CE16D77A-E364-4ACD-948B-1EB6218B0EA3}</ProjectGUID>
        <TargetFrameworkVersion>3.5</TargetFrameworkVersion>
        <Keyword>ManagedCProj</Keyword>
        <RootNamespace>CPP_Test</RootNamespace>
      </PropertyGroup>
    ```

7.  Uložte a zavřete soubor VCXPROJ.

8.  V Průzkumníku řešení, zvolte Výběr **znovu načíst projekt** z místní nabídky vaší nové testovacího projektu Visual C++.

## <a name="see-also"></a>Viz také

- [Vytvoření řešení služby SharePoint](/office-dev/office-dev/create-sharepoint-solutions)
- [Sestavování a ladění řešení služby SharePoint](/office-dev/office-dev/building-and-debugging-sharepoint-solutions)
- [Dialogové okno Pokročilé nastavení kompilátoru (Visual Basic)](../ide/reference/advanced-compiler-settings-dialog-box-visual-basic.md)
