---
title: Nasazení řešení Office s použitím Instalační služby systému Windows | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, setup project
- Office development in Visual Studio, MSI
- deploying applications [Office development in Visual Studio], setup project
- deploying applications [Office development in Visual Studio], MSI
- ClickOnce deployment [Office development in Visual Studio], MSI
- publishing Office solutions [Office development in Visual Studio], setup project
- Office applications [Office development in Visual Studio], MSI
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: f2c51b101b890a2aaf2ea63edfd1f55d05abe18e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="deploying-an-office-solution-by-using-windows-installer"></a>Nasazení řešení Office s použitím Instalační služby systému Windows
Naučte se vytvářet Instalační služby systému Windows pro řešení Office s použitím [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)].  
  
Pomocí sady Visual Studio k vytvoření instalační služby systému Windows, můžete nasadit řešení Office vyžadující přístup pro správu v počítači koncového uživatele. Například můžete takový soubor instalaci řešení jenom jednou pro všechny uživatele počítače. Můžete také nasadit řešení Office s použitím technologie ClickOnce, ale tato řešení je nutné nainstalovat samostatně pro každého uživatele počítače.  
  
  
## <a name="in-this-topic"></a>V tomto tématu  
  
- [Stáhněte si ukázky doplňku VSTO](#Download)  
  
- [Získat InstallShield Limited Edition](#Obtain)  
  
- [Určete, jak chcete udělit vztah důvěryhodnosti k řešení](#ApplySecurity)  
  
- [Vytvořte projekt instalace](#Create)  
  
- [Přidat výstup projektu](#Add)  
  
- [Přidat manifesty nasazení a aplikací](#AddD)  
  
- [Konfigurace závislých součástí jako předpoklady](#Configure)  
  
- [Zadejte, kam chcete nasadit řešení na počítači uživatele](#Location)  
  
- [Konfigurace doplňku VSTO](#ConfigureRegisitry)  
  
- [Konfigurace přizpůsobení na úrovni dokumentu](#ConfigureDocument)  
  
- [Sestavení projektu instalace](#Build)  
  
Další informace o nasazení řešení Office s použitím technologie ClickOnce najdete v tématu [nasazení řešení Office aplikací ClickOnce pomocí](../vsto/deploying-an-office-solution-by-using-clickonce.md).  
  
Informace o tom, jak vytvořit soubor Instalační služby systému Windows pomocí [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)], najdete v části [nasazení Visual Studio 2010 Tools pro sadu Office řešení pomocí Instalační služby systému Windows](http://go.microsoft.com/fwlink/?LinkId=201807).  
  
  
## <a name="Download"></a>Stažení ukázky  
Toto téma se odkazuje na následující ukázky ke stažení.  
  
  
  
|Ukázka<br /><br />|Popis<br /><br />|  
|----------|---------------|  
|[ExcelAddIn](http://go.microsoft.com/fwlink/?LinkID=275492)<br /><br />|VSTO pro Excel doplněk, který můžete nainstalovat na počítač, který spouští 32bitové nebo 64bitové verze systému Office.<br /><br />|  
|[ExcelWorkbook](http://go.microsoft.com/fwlink/?LinkID=275493)<br /><br />|Přizpůsobení na úrovni dokumentu aplikace Excel, kterou lze nainstalovat do počítače, který spouští 32bitové nebo 64bitové verze systému Office.<br /><br />|  
  
## <a name="ApplySecurity"></a>Určete, jak chcete udělit vztah důvěryhodnosti k řešení  
Před spuštěním řešení v uživatelských počítačích, musí udělit vztah důvěryhodnosti v některém z následujících způsobů nebo uživatelé musí odpovídat na výzvu vztahu důvěryhodnosti, při instalaci řešení.  
  
  
- Podepisování manifestů pomocí certifikátu, který identifikuje známé a důvěryhodné vydavatele. Další informace najdete v tématu [důvěřující řešení pomocí podepisování aplikace a manifesty nasazení](../vsto/granting-trust-to-office-solutions.md#Signing).  
  
- Nainstalujte řešení k adresáři Program Files na počítači uživatele.  
  
> [!NOTE]  
> Pro úpravy na úrovni dokumentů musí být umístění dokumentu také důvěryhodný. Další informace najdete v tématu [udělení vztah důvěryhodnosti s dokumenty](../vsto/granting-trust-to-documents.md).  
  
  
## <a name="Obtain"></a>Získat InstallShield Limited Edition  
Soubor Instalační služby systému Windows můžete vytvořit pomocí InstallShield Limited Edition (MANSKÁ), což je bezplatná, pokud jste nainstalovali Visual Studio. MANSKÁ nahrazuje funkci šablony projektů pro instalaci a nasazení, které nabízí předchozí verze sady Visual Studio.  
  
  
#### <a name="to-get-installshield-limited-edition"></a>Chcete-li získat InstallShield Limited Edition  
  
1. Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
   **Nový projekt** otevře se dialogové okno.  
  
2. Rozbalte v podokně šablon **jiné typy projektů**a potom zvolte **instalace a nasazení** šablony.  
  
3. V seznamu typy projektů pro **instalace a nasazení**, zvolte **Povolit InstallShield Limited Edition**a potom zvolte **OK** tlačítko.  
  
   Zobrazí se stránka s informacemi o tom, jak získat InstallShield Limited Edition.  
  
4. Na této stránce zvolte **přejít na web stažení** odkaz.  
  
5. Na stránce pro stahování pro InstallShield Limited Edition, zadejte požadované informace do příslušných polí a potom zvolte **stáhnout nyní** odkaz.  
  
   Po stažení, instalace a aktivace produktu, **projekt InstallShield Limited Edition** šablona zobrazuje v sadě Visual Studio.  
  
  
## <a name="Create"></a>Vytvořte projekt instalace  
  
####   
1. V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], otevřete projekt Office, kterou chcete nasadit.  
  
   Ukázky VSTO Add-in, které jsou spojeny s tímto tématem obsahovat projektu s názvem **ExcelAddIn**. Přizpůsobení na úrovni dokumentu ukázky obsahovat projektu s názvem **ExcelWorkbook**. Toto téma bude odkazovat pomocí jedné z těchto dvou názvy projektů Office ve vašem řešení.  
  
2. Na řádku nabídek zvolte **soubor**, **přidat**, **nový projekt**.  
  
   **Přidat nový projekt** otevře se dialogové okno.  
  
3. Rozbalte v podokně šablon **jiné typy projektů**a potom zvolte **instalace a nasazení** šablony.  
  
4. V seznamu typy projektů pro **instalace a nasazení**, zvolte **projekt InstallShield Limited Edition**, název projektu a potom zvolte **OK** tlačítko.  
  
   Projekt instalace InstallShield, kterou jste právě vytvořili, zobrazí se ve vašem řešení.  
  
   Ukázky pro toto téma obsahuje projekt instalace, který je pojmenován **OfficeAddInSetup**. Toto téma bude odkazovat na projekt instalace ve vašem řešení pomocí se stejným názvem.  
  
  
## <a name="Add"></a>Přidat výstup projektu  
Můžete nakonfigurovat **OfficeAddInSetup** projekt zahrnoval výstup projektu Office. Pro projekty doplňku VSTO výstupu projektu @ je pouze sestavení řešení. Pro přizpůsobení na úrovni dokumentu projekty výstupu projektu @ obsahuje pouze sestavení řešení, ale také samotného dokumentu.  
  
  
#### <a name="to-add-the-project-output"></a>Chcete-li přidat výstup projektu  
  
1. V **Průzkumníku řešení**, rozbalte **OfficeAddInSetup** uzel projektu a potom zvolte **projektu pomocníka** souboru, který znázorňuje následující obrázek.  
  
   ![Projekt pomocníka soubor v Průzkumníku řešení](../vsto/media/installshield-projectassistant.png "projektu pomocníka soubor v Průzkumníku řešení")  
  
2. Na řádku nabídek zvolte **zobrazení**, **otevřete**.  
  
3. V dolní části **projektu pomocníka** vyberte **soubory aplikace** tlačítko, které na následujícím obrázku.  
  
   ![Tlačítko soubory aplikace. ] (../vsto/media/installshield-applicationfiles.png "Tlačítko the soubory aplikace.")  
  
4. V **soubory aplikace** vyberte **přidejte výstupy projektu** tlačítko.  
  
5. V **Visual Studio výstup selektor** dialogové okno, vyberte **primárního výstupního** zaškrtněte políčko a potom vyberte **OK** tlačítko.  
  
  
## <a name="AddD"></a>Přidat manifesty nasazení a aplikací  
  
####   
1. V **soubory aplikace** vyberte **přidat soubory** tlačítko.  
  
2. V **otevřete** dialogové okno, přejděte do výstupního adresáře **ExcelAddIn** projektu.  
  
   Výstupní adresář je obvykle **bin\release** podsložky kořenového adresáře projektu, v závislosti na konfiguraci sestavení, který zvolíte.  
  
3. V adresáři výstup, vyberte **ExcelAddIn.vsto** a **ExcelAddIn.dll.manifest** soubory a potom vyberte **otevřete** tlačítko.  
  
   **Soubory aplikace** stránka nyní obsahuje výstupního souboru projektu, manifest nasazení a manifest aplikace, jak ukazuje následující obrázek.  
  
   ![Výstupní soubory projektu instalace. ] (../vsto/media/installshield-outputfiles.png "Výstupních souborů projektu instalace.")  
  
  
## <a name="Configure"></a>Konfigurace závislých součástí jako předpoklady  
Instalační program aplikace musí obsahovat pouze následující součásti, ale také všechny ostatní součásti, které jsou požadované pro vaše řešení ke spuštění.  
  
  
- Verze rozhraní .NET Framework, vaše cíle řešení Office.  
  
- Microsoft Visual Studio 2010 Tools for Office Runtime.  
  
  
### <a name="add-the-net-framework-4-or-the-net-framework-45-as-a-prerequisite"></a>Předpokladem je přidat rozhraní .NET Framework 4 nebo .NET Framework 4.5  
  
#####   
1. V **Průzkumníku řešení**, rozbalte **OfficeAddInSetup** uzel projektu, rozbalte položku **zadejte Data aplikací** uzel a potom vyberte  **Redistributables** souboru, který znázorňuje následující obrázek.  
  
   ![V Průzkumníku řešení soubor Redistributables](../vsto/media/installshield-redistributablesfile.png "Redistributables soubor v Průzkumníku řešení")  
  
2. Na řádku nabídek zvolte **zobrazení**, **otevřete**.  
  
   **Redistributables** otevře se stránka.  
  
3. V seznamu distribuovatelné součásti, vyberte příslušný zaškrtnutí políčka pro verzi rozhraní .NET Framework, vaše řešení cíle.  
  
   Například pokud vaše řešení cíle [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)], vyberte **Microsoft .NET Framework 4.5 Full** zaškrtávací políčko. Může zobrazit dialogové okno s dotazem, zda chcete instalace distribuovatelné součásti, které InstallShield vyžaduje před předpokladem je přidat součást. Pokud toto dialogové okno se nezobrazí, součást již existuje ve vašem počítači.  
  
4. Pokud se zobrazí toto dialogové okno, vyberte **ne** tlačítko.  
  
  
### <a name="AddToolsForOffice"></a>Přidat sadu Visual Studio 2010 Tools for Office Runtime  
**Redistributables** stránka obsahuje položku s názvem **Microsoft VSTO 2010 Runtime**, ale odkazuje na starší verzi modulu runtime. Proto může ručně vytvořit konfigurační soubor, který odkazuje na nejnovější verzi. Tento soubor pak musíte umístit do stejného adresáře jako konfigurační soubory pro všechny ostatní položky, které se zobrazují v **Redistributables** stránky.  
  
  
##### <a name="to-add-the-visual-studio-2010-tools-for-office-runtime-as-a-prerequisite"></a>Chcete-li přidat sadu Visual Studio 2010 Tools for Office Runtime předpokladem je  
  
1. Otevřete Poznámkový blok a potom vložte následující kód XML do textového souboru.  
  
  
   ```xml  
   <?xml version="1.0" encoding="UTF-8"?>  
   <SetupPrereq>  
   <conditions>  
       <condition Type="32" Comparison="2" Path="HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VSTO Runtime Setup\v4R" FileName="Version" ReturnValue="10.0.50903" Bits="2"></condition>  
   <condition Type="32" Comparison="2" Path="HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VSTO Runtime Setup\v4R" FileName="Version" ReturnValue="10.0.50903" Bits="2"></condition>  
   </conditions>  
   <files>  
       <file LocalFile="<ISProductFolder>\SetupPrerequisites\VSTOR\vstor_redist.exe" URL="http://download.microsoft.com/download/C/0/0/C001737F-822B-48C2-8F6A-CDE13B4B9E9C/vstor_redist.exe" CheckSum="88b8aa9e8c90818f98c80ac4dd998b88" FileSize=" 0,40117912"></file>  
   </files>  
   <execute file="vstor_redist.exe" returncodetoreboot="1641,3010" requiresmsiengine="1">  
   </execute>  
   <properties Id="{15965040-56BB-49B8-A88F-3525C48D9BA8}" Description="This prerequisite installs the most recent version of the Microsoft Visual Studio 2010 Tools for Office Runtime." >  
   </properties>  
     
   </SetupPrereq>  
   ```  
  
2. Generovat identifikátor GUID v sadě Visual Studio. Na **nástroje** nabídce zvolte **vytvořit GUID**.  
  
3. V **GUID generátor** programu, vyberte **registru formátu** možnost tlačítko, vyberte **kopie** tlačítko a potom vyberte **ukončení** tlačítko.  
  
4. V poznámkovém bloku, nahraďte text **zde bude vaše GUID** vložením identifikátor GUID na příslušné místo.  
  
   **&lt;Vlastnosti&gt;** element souboru podobá následující zprávě.  
  
  
   ```xml  
   <properties Id="{87989B73-21DC-4403-8FD1-0C68A41A6D8C}" Description="This prerequisite installs the most recent version of the Microsoft Visual Studio 2010 Tools for Office Runtime." >  
   </properties>  
   ```  
  
5. V řádku nabídek v programu Poznámkový blok, zvolte **soubor**, **Uložit**.  
  
6. V **uložit jako** dialogové okno, přejděte k vaší **plochy** složky.  
  
7. V **uložit jako typ** vyberte **všechny soubory (&#42;.&#42;)** .  
  
8. V **název souboru** zadejte **Visual Studio 2010 Tools for Office Runtime.prq**a potom zvolte **Uložit** tlačítko.  
  
   > [!NOTE]  
   >    Ujistěte se, že přidáte **.prq** na konci názvu souboru pro identifikaci tento soubor jako požadovaný soubor.  
  
9. Zavřete poznámkový blok.  
  
10. Z vaší **plochy** složku, zkopírujte Visual Studio 2010 Tools for Office Runtime.prq souboru do jednoho z následujících adresářů v počítači.  
  
   Pro 32bitové operační systémy: %ProgramFiles%\InstallShield\2013LE\SetupPrerequisites\  
  
   Pro 64bitové operační systémy: % ProgramFiles (x86) %\2013LE\SetupPrerequisites\  
  
11. V **Redistributable** stránky InstallShield projekt, vyberte **aktualizovat** tlačítko pro aktualizaci seznamu distribuovatelné součásti, jak ukazuje následující obrázek.  
  
   ![Tlačítko Aktualizovat. ] (../vsto/media/installshield-refreshbutton.png "Tlačítko Aktualizovat.")  
  
12. V seznamu distribuovatelné součásti, vyberte **Visual Studio 2010 Tools for Office Runtime** zaškrtávací políčko.  
  
   Dialogové okno může se objevit dotazem, zda chcete nainstalovat součást redistributable. Pokud toto dialogové okno se nezobrazí, můžete přeskočit na [zadejte, kam chcete nasadit řešení na počítači uživatele](#Location) části tohoto tématu.  
  
13. Pokud se zobrazí toto dialogové okno, vyberte **ne** tlačítko.  
  
  
## <a name="Location"></a>Zadejte, kam chcete nainstalovat řešení na počítači uživatele  
  
####   
1. V **Průzkumníku řešení**, rozbalte **OfficeAddInSetup** uzlu, rozbalte **uspořádání vašeho nastavení** uzlu a potom vyberte **obecné informace** souboru.  
  
2. Na řádku nabídek zvolte **zobrazení**, **otevřete**.  
  
3. V seznamu vlastností zvolte **Procházet** vedle položky **INSTALLDIR** vlastnost.  
  
4. V **nastavit INSTALLDIR** dialogové okno pole, zvolte složku v počítači uživatele, ve které chcete nainstalovat řešení.  
  
   > [!NOTE]  
   >    Můžete také vytvořit podadresáře v **nastavit INSTALLDIR** dialogové okno otevřením místní nabídku pro libovolné složky v seznamu.  
  
  
## <a name="ConfigureRegisitry"></a>Konfigurace doplňku VSTO  
Můžete zadat, zda chcete doplňku VSTO nainstalují pro všechny uživatele počítače (pro počítač), nebo jenom pro uživatele provádějící instalaci (pro jednotlivé uživatele).  
  
Pokud chcete pro podporu instalace jednotlivé počítače, vytvořte dva samostatné instalační programy. Instalační programy založené na verzi Office (32bitové a 64bitové verze) nebo na verzi systému Windows (32bitové a 64bitové verze) můžete rozdělit uživatele se systémem.  
  
Instalace pro jednotlivé uživatele vyžadují jenom jeden instalační program bez ohledu na verzi Office nebo Windows.  
  
> [!NOTE]  
> Tato část se týká pouze v případě, že nasazujete doplňku VSTO. Pokud nasazujete přizpůsobení na úrovni dokumentu, můžete okamžitě přejít na [konfigurace přizpůsobení na úrovni dokumentu](#ConfigureDocument) části.  
  
  
#### <a name="to-specify-whether-you-want-to-support-per-user-or-per-computer-installations"></a>Chcete-li určit, zda chcete podporovat jednotlivé uživatele nebo pro počítač instalací  
  
1. V **Průzkumníku řešení**, rozbalte **OfficeAddInSetup** uzel projektu, rozbalte položku **uspořádání vaše instalace** uzel a potom vyberte **obecné informace**  souboru.  
  
2. Na řádku nabídek zvolte **zobrazení**, **otevřete**.  
  
   Vlastnosti projektu instalace se zobrazí.  
  
3. V seznamu **AllUSERS** vlastnost, určete, zda má být nainstalován pro všechny uživatele počítače, nebo pouze uživatele, který nainstaluje řešení toto řešení.  
  
   Chcete-li nainstalovat doplněk VSTO pro aktuálního uživatele, zvolte **ALLUSERS = "" (instalace pro jednotlivé uživatele)**. Chcete-li nainstalovat doplněk VSTO pro všechny uživatele počítače, zvolte **ALLUSERS = 1 (instalace vázaná na počítač)**  
  
   V dalším postupu vytvoříte klíče registru se zapnout aplikaci Office zjišťovat a načíst doplňku VSTO. V tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
  
#### <a name="to-create-registry-keys"></a>K vytvoření klíče registru  
  
1. V **Průzkumníku řešení**, vyberte **projektu pomocníka** uzlu.  
  
   Na řádku nabídek zvolte **zobrazení**, **otevřete**.  
  
2. V dolní části **projektu pomocníka** vyberte **registru aplikace** tlačítko, které na následujícím obrázku.  
  
   ![Tlačítko Express registru. ] (../vsto/media/installshield-applicationregistry.gif "Registru Express tlačítko.")  
  
   **Aplikace registru** se zobrazí stránka.  
  
3. V části **chcete nakonfigurovat dat registru, který bude instalovat aplikace?**, vyberte **Ano** tlačítko.  
  
4. V **zobrazení registru cílového počítače** seznamu, přidejte klíče hierarchie, která umožňuje typ instalačního programu, kterou chcete vytvořit.  
  
   Cesta, která nakonfigurujete v této části závisí na tom, jestli vytvořit instalační program na uživatele nebo instalační program pro počítač.  
  
   **Instalační program na uživatele**  
  
   **HKEY_CURRENT_USER\Software\Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**  
  
   **Instalační programy jednotlivé počítače založené na verzi Office**  
  
  
  
|Verze systému Office<br /><br />|Cesta konfigurace InstallShield<br /><br />|  
|------------------|------------------------------------|  
|32bitová<br /><br />|**HKEY_LOCAL_MACHINE\Software(32-bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />|  
|64bitových<br /><br />|**HKEY_LOCAL_MACHINE\Software(64-Bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />|  
   **Instalační programy na počítači podle verze systému Windows**  
  
  
  
|Verze systému Windows<br /><br />|Cesta konfigurace InstallShield<br /><br />|  
|-------------------|------------------------------------|  
|32bitová<br /><br />|**HKEY_LOCAL_MACHINE\Software(32-bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />|  
|64bitových<br /><br />|**HKEY_LOCAL_MACHINE\Software(32-bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />**HKEY_LOCAL_MACHINE\Software(64-Bit) \Microsoft\Office\Excel\Addins\SampleCompany.ExcelAddIn**<br /><br />|  
   > [!NOTE]  
   >    Instalační program pro 64bitový systém Windows vyžaduje dvě cesty registru, protože je možné uživatelům spouštět 32bitové a 64bitové verze Office na počítači, na kterém běží 64bitová verze Windows.  
  
   > [!NOTE]  
   >    Jako osvědčený postup začněte název vaší doplňku VSTO název vaší společnosti. Touto konvencí zvyšuje šance, že bude jedinečný klíč a snižuje riziko jsou v konfliktu s doplňku VSTO od jiného dodavatele. Doplňky, které mají stejný název, například přepíše druhé strany registrační kódy. Tento přístup nemůže zaručit, že bude jedinečný klíč, ale může snížit potenciální kolize názvů.  
  
5. Po vytvoření hierarchie klíčů, otevřete místní nabídku pro **SampleCompany.ExcelAddIn** klíče, zvolte **nový**a potom zvolte **řetězcovou hodnotu**.  
  
   Nová hodnota se zobrazí v **dat registru cílového počítače** seznamu. Název hodnoty řetězce zvýrazní, aby ho mohli přejmenovat.  
  
6. Hodnota, která má přejmenovat **popis**.  
  
7. Opakujte tento postup k vytvoření následujících hodnot.  
  
  
  
|Typ hodnoty<br /><br />|Název<br /><br />|  
|--------------|--------|  
|Řetězcová hodnota<br /><br />|**FriendlyName**<br /><br />|  
|Přidejte hodnotu DWORD<br /><br />|**LoadBehavior –**<br /><br />|  
|Řetězcová hodnota<br /><br />|**Manifest**<br /><br />|  
  
8. Otevřete místní nabídku pro **popis** hodnoty a potom vyberte **upravit**.  
  
   **Upravit Data** zobrazí se dialogové okno.  
  
9. V **údaj hodnoty** textové pole, zadejte **Add-In ukázkové aplikace Excel**a potom vyberte **OK** tlačítko.  
  
   Tento popis se zobrazí, když uživatel otevře aplikaci Office, otevře se okno **možnosti** dialogové okno a pak na **doplňky** podokně zvolí doplňku VSTO.  
  
10. Otevřete místní nabídku pro **FriendlyName** hodnoty a potom vyberte **upravit**.  
  
   **Upravit Data** zobrazí se dialogové okno.  
  
11. V **údaj hodnoty** textové pole, zadejte **Add-In ukázkové aplikace Excel**a potom vyberte **OK** tlačítko.  
  
   Tento řetězec je zobrazen v **COM Doplňky** dialogové okno v aplikaci Office. Ve výchozím nastavení hodnota řetězce, je ID VSTO Add-in.  
  
12. Otevřete místní nabídku pro **LoadBehavior** hodnoty a potom vyberte **upravit**.  
  
   **Upravit Data** zobrazí se dialogové okno.  
  
13. V **údaj hodnoty** textové pole, zadejte **3**a potom vyberte **OK** tlačítko.  
  
   Hodnota 3 načte doplňku VSTO při spuštění aplikace. Další informace o hodnotách LoadBehavior najdete v tématu [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
14. Otevřete místní nabídku pro **Manifest** hodnoty a potom vyberte **upravit**.  
  
   **Upravit Data** zobrazí se dialogové okno.  
  
15. V **údaj hodnoty** textové pole, zadejte **file:///[INSTALLDIR]ExcelAddIn.vsto|vstolocal**a potom vyberte **OK** tlačítko.  
  
   Visual Studio 2010 Tools for Office Runtime používá tuto cestu k vyhledání manifestu nasazení. **[INSTALLDIR]** část této cesty je makro, která se mapuje na **INSTALLDIR** vlastnost **obecné informace** stránce vlastností projektu InstallShield instalační program. Tato vlastnost určuje umístění na cílovém počítači pro instalaci doplňku VSTO. **| Vstolocal** příponu zajistí, že vaše řešení je načtena z instalační složky, není mezipaměti ClickOnce.  
  
> [!IMPORTANT]  
> Pokud vytvoříte vlastní formulář oblast v doplňku VSTO pro Outlook, musíte vytvořit další položky registru k registraci oblasti v aplikaci Outlook. Další informace najdete v tématu [položky registru pro oblastí formulářů aplikace Outlook](../vsto/registry-entries-for-vsto-add-ins.md#OutlookEntries).  
  
  
## <a name="ConfigureDocument"></a>Konfigurace přizpůsobení na úrovni dokumentu  
Tato část se týká pouze v případě, že nasazujete přizpůsobení na úrovni dokumentu. Pokud nasazujete doplňku VSTO, můžete přejít na okamžitě [sestavení projektu instalace](#Build) části.  
  
Úpravy na úrovni dokumentů nepoužívejte klíče registru. Vlastní vlastnosti dokumentu místo toho obsahují umístění manifestu nasazení.  
  
Chcete-li upravit vlastní vlastnosti, vytvořte program, který odebere přizpůsobení na úrovni dokumentu z dokumentu, upraví příslušné vlastnosti a znovu připojí přizpůsobení v dokumentu. Potom můžete vytvářet vlastní akce, který spouští program, a přidáte do projektu instalace této akce.  
  
  
#### <a name="to-create-a-program-that-modifies-document-properties"></a>Vytvoření programu, která upraví vlastnosti dokumentu  
  
1. Na řádku nabídek zvolte **soubor**, **přidat**, **nový projekt**.  
  
   **Přidat nový projekt** zobrazí se dialogové okno.  
  
2. V podokně šablon v uzlu pro jazyk, který chcete použít, vyberte **Windows** složky.  
  
3. V seznamu typy projektů pro **Windows**, vyberte **konzolové aplikace** šablony.  
  
4. Název projektu **SetExcelDocumentProperties**a potom zvolte **OK** tlačítko.  
  
5. V **Průzkumníku řešení**, vyberte **zobrazit všechny soubory** tlačítko, otevřete místní nabídku pro **SetExcelDocumentProperties** uzel projektu a potom zvolte **Přidat odkaz**.  
  
6. V **správce odkazů** dialogovém okně vyberte **rozšíření** kartě a potom zaškrtněte políčko vedle následující sestavení a potom zvolte **OK** tlačítko.  
  
  
   - Microsoft.VisualStudio.Tools.Applications.Runtime  
  
   - Microsoft.VisualStudio.Tools.Applications.ServerDocument  
  
7. V **Průzkumníku řešení**, vyberte **Program.cs** souboru (C# aplikace) nebo **Module1.vb** souboru (pro aplikace Visual Basic).  
  
8. Na řádku nabídek zvolte **zobrazení**, **otevřete**.  
  
9. Obsah celý soubor nahraďte následujícím kódem.  
  
[!code-vb[Trin_CustomAction#1](../vsto/codesnippet/VisualBasic/setexceldocumentproperties/module1.vb#1)]
[!code-csharp[Trin_CustomAction#1](../vsto/codesnippet/CSharp/setexceldocumentproperties/program.cs#1)]  
  
10. Kompilace projektu.  
  
  
#### <a name="to-add-a-custom-action-that-runs-your-program"></a>Chcete-li přidat vlastní akci, která spustí program  
  
1. V **Průzkumníku řešení**, rozbalte **OfficeAddInSetup** uzel projektu a potom zvolte **projektu pomocníka** souboru, který znázorňuje následující obrázek.  
  
   ![Projekt pomocníka soubor v Průzkumníku řešení](../vsto/media/installshield-projectassistant.png "projektu pomocníka soubor v Průzkumníku řešení")  
  
2. Na řádku nabídek zvolte **zobrazení**, **otevřete**.  
  
3. V dolní části **projektu pomocníka** vyberte **soubory aplikace** tlačítko, které na následujícím obrázku.  
  
   ![Tlačítko soubory aplikace. ] (../vsto/media/installshield-applicationfiles.png "Tlačítko the soubory aplikace.")  
  
4. V **soubory aplikace** vyberte **přidejte výstupy projektu** tlačítko.  
  
   **Visual Studio výstup selektor** zobrazí se dialogové okno.  
  
5. V části **SetExcelDocumentProperties** uzlu, vyberte **primárního výstupního** zaškrtněte políčko a potom vyberte **OK** tlačítko.  
  
6. V **Průzkumníku řešení**v části **OfficeAddInSetup** uzlu, rozbalte **definovat nastavení požadavků a akce** uzel a potom vyberte **vlastní Akce** složky.  
  
7. Na řádku nabídek zvolte **zobrazení**, **otevřete**.  
  
   Seznam událostí se zobrazí v podokně na straně obrazovky.  
  
   > [!NOTE]  
   >    Pouze několik událostí, které se zobrazují v tomto seznamu jsou k dispozici v InstallShield Limited Edition. V tomto postupu spustíte program pomocí **dialogové okno po instalaci informací o úspěšném dokončení** událostí.  
  
8. V seznamu událostí v části **vlastní akce během instalace**, otevřete místní nabídku pro **dialogové okno po instalaci informací o úspěšném dokončení** události a potom zvolte **nové EXE**.  
  
   Vlastní akce, který je pojmenován **NewCustomAction1** se zobrazí pod **dialogové okno po instalaci informací o úspěšném dokončení** událostí. V podokně vedle události se zobrazí sadu vlastností pro vlastní akci.  
  
   > [!IMPORTANT]  
   >    Dva **dialogové okno po instalaci informací o úspěšném dokončení** události se zobrazí v seznamu událostí. Ujistěte se, že zvolíte instanci **dialogové okno po instalaci informací o úspěšném dokončení** událost, která se zobrazí pod **vlastní akce během instalace** uzlu.  
  
9. V seznamu **umístění zdroje** vlastnost, zvolte **nainstalovány s produktem**.  
  
10. Vyberte **Procházet** vedle položky **název souboru** vlastnost.  
  
11. V **vyhledejte cílový soubor** dialogové okno, procházet a **SetExcelDocumentProperties.Primary.output** souboru a potom vyberte **otevřete** tlačítko.  
  
   Umístění tohoto souboru závisí na složku, která jste zadali pro **INSTALLDIR** vlastnosti projektu instalace. Například pokud nastavíte tuto vlastnost na složku s názvem **[PersonalFolder] DemoWorkbookApp**, můžete najít **SetExcelDocumentProperties.Primary.output** soubor procházením **[ProgramFilesFolder] \DemoWorkbookApp**.  
  
   V několika dalších krocích můžete získat ID řešení dokumentu a poté předat toto ID jako parametr konzolové aplikace. Budete také předat umístění dokumentu, manifest nasazení a sestavení dokumentu.  
  
12. Otevřete místní nabídku pro **ExcelWorkbook** projektu a potom vyberte **otevřít složku v Průzkumníku Windows** nebo **otevřít složku v Průzkumníku souborů** v závislosti na vaší operační systém.  
  
   Otevře složku, která obsahuje vaše řešení.  
  
13. V poznámkovém bloku otevřete soubor projektu vašeho řešení. Projekty Visual Basic je název souboru ExcelWorkbook.vbproj. Pro projekty C# název souboru je ExcelWorkbook.csproj.  
  
14. Vyhledejte v souboru projektu **&lt;SolutionID&gt;** elementu, zkopírujte jeho hodnotu do schránky a pak zavřete poznámkový blok.  
  
   Předat tuto hodnotu do konzoly aplikace jako parametr.  
  
15. Na stránce vlastnosti **NewCustomAction1**, nastavte **příkazového řádku** vlastnost, která má následující řádek textu.  
  
  
   ```  
   /assemblyLocation="[INSTALLDIR]ExcelWorkbook.dll" /deploymentManifestLocation="[INSTALLDIR]ExcelWorkbook.vsto" /documentLocation="[INSTALLDIR]ExcelWorkbook.xlsx" /solutionID="Your Solution ID"  
   ```  
  
16. Nahraďte **vaše ID řešení** s ID řešení, které jste zkopírovali do schránky.  
  
   > [!IMPORTANT]  
   >    Otestujte instalačním programem vaší ověřte, že konzolovou aplikaci, která se spouští tato vlastní akce přístup dokumenty v adresáři [INSTALLDIR]. Přístup pro správu (například adresář Program Files) může vyžadovat některé adresářů v počítači uživatele. Pokud nasazujete řešení do adresáře, který vyžaduje přístup pro správu, by měla otevřít **vlastnosti** dialogové okno souboru setup.exe, vyberte **kompatibility** a potom vyberte **spustit tento program jako správce** políčko před distribucí Instalační služby. Pokud nechcete, aby uživatelům spustit instalační program oprávnění ke správě, nastavte vlastnost [INSTALLDIR] do adresáře, ke které má uživatel pravděpodobně přístup již, jako **dokumenty** adresáře. Další informace najdete v tématu [určit, ve které chcete nainstalovat řešení na počítači uživatele](#Location) části tohoto tématu.  
  
  
## <a name="Build"></a>Sestavení projektu instalace  
  
####   
1. V **Průzkumníku řešení**, rozbalte **Příprava pro verzi** uzel a potom zvolte **verze** souboru.  
  
2. Na řádku nabídek zvolte **zobrazení**, **otevřete**.  
  
   **Sestavení** explorer se otevře v podokně úloh, ve kterém můžete si zvolit typ verze, kterou chcete vytvořit.  
  
3. V **sestavení** explorer, vyberte **SingleImage** složky.  
  
4. V podokně vedle **sestavení** explorer, vyberte **Setup.exe** kartě.  
  
5. V **Setup.exe** stránka vlastností z **InstallShield požadavky umístění** vyberte **stáhnout z webu**.  
  
6. Na řádku nabídek zvolte **sestavení**, **nástroje Configuration Manager**.  
  
7. V **aktivní konfigurace řešení** vyberte **SingleImage**.  
  
8. V **projektu kontexty** tabulky v **konfigurace** sloupec **OfficeAddInSetup** projektu, zvolte **SingleImage**a potom Vyberte **Zavřít** tlačítko.  
  
9. Na řádku nabídek zvolte **sestavení**, **sestavení OfficeAddInSetup**.  
  
   Po dokončení sestavení, můžete vyhledat soubor setup.exe **OfficeAddInSetup** projektu v následujícím umístění: *OfficeAddInSetupProjectRoot *** \OfficeAddInSetup\Express\SingleImage\DiskImages\ DISK 1\**  
  
  
## <a name="see-also"></a>Viz také  
[Požadavky na řešení Office nasazení](http://msdn.microsoft.com/en-us/library/9f672809-43a3-40a1-9057-397ce3b5126e)  
[Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
[Položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md)  
[Přehled přizpůsobených vlastností dokumentu](../vsto/custom-document-properties-overview.md)  
[Udělení důvěry řešením pro systém Office](../vsto/granting-trust-to-office-solutions.md)  
[Udělení důvěry dokumentům](../vsto/granting-trust-to-documents.md)  
[Nasazení aplikace Visual Studio 2010 Tools pro řešení Office pomocí Instalační služby systému Windows](http://go.microsoft.com/fwlink/?LinkId=201807)  
  
