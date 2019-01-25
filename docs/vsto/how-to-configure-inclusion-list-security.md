---
title: 'Postupy: Konfigurace zabezpečení se seznamem povolených položek'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- permissions [Office development in Visual Studio
- inclusion lists [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6c8ea1c94254bc37edc15e0c267592e921003426
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54868677"
---
# <a name="how-to-configure-inclusion-list-security"></a>Postupy: Konfigurace zabezpečení se seznamem povolených položek
  Pokud máte oprávnění správce, můžete nakonfigurovat [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěryhodný dotaz na ovládací prvek, zda koncovým uživatelům se zobrazí možnost instalace řešení pro systém Office uložením rozhodnutí o důvěryhodnosti na seznam povolených položek. Informace o seznamech povolených položek najdete v tématu [řešení důvěřovat Office s použitím seznamů povolených položek](../vsto/trusting-office-solutions-by-using-inclusion-lists.md).  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Pro řešení, které jsou v každé z pěti zóny můžete nastavit následující možnosti:  
  
-   Povolit [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěřovat výzvy klíč a seznam povolených položek. Můžete povolit koncovým uživatelům zajištění důvěryhodnosti řešení pro systém Office, které jsou podepsané pomocí žádné certifikáty.  
  
-   Omezit [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěřovat výzvy klíč a seznam povolených položek. Můžete povolit koncovým uživatelům pro instalaci řešení pro systém Office, které jsou podepsány pomocí certifikátu, který identifikuje vydavatele, ale který ještě není důvěryhodný.  
  
-   Zakažte [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] důvěřovat výzvy klíč a seznam povolených položek. Znemožněte koncovým uživatelům instalovat žádné řešení pro Office, které není podepsáno s explicitně důvěryhodný certifikát.  
  
## <a name="enable-the-inclusion-list"></a>Povolit seznam povolených položek  
 Povolte seznamu povolených položek pro zónu, když chcete koncovým uživatelům se zobrazí možnost instalace a spuštění jakékoli řešení pro Office, který pochází z této zóny.  
  
### <a name="to-enable-the-inclusion-list-by-using-the-registry-editor"></a>Chcete-li povolit seznam povolených položek pomocí Editoru registru  
  
1.  Otevřete editor registru:  
  
    1.  Klikněte na tlačítko **Start**a potom klikněte na tlačítko **spustit**.  
  
    2.  V **otevřít** zadejte **regedt32.exe**a potom klikněte na tlačítko **OK**.  
  
2.  Vyhledejte následující klíč registru:  
  
     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\.NETFramework\Security\TrustManager\PromptingLevel**  
  
     Pokud klíč neexistuje, vytvořte ho.  
  
3.  Přidejte následující podklíče jako **řetězcovou hodnotu**, pokud ještě neexistují, s přiřazenými hodnotami.  
  
    |Hodnota řetězce podklíče|Hodnota|  
    |-------------------------|-----------|  
    |**Internet**|**AuthenticodeRequired**|  
    |**UntrustedSites**|**Disabled** (Zakázáno)|  
    |**MyComputer**|**Povoleno**|  
    |**LocalIntranet**|**Povoleno**|  
    |**TrustedSites**|**Povoleno**|  
  
     Ve výchozím nastavení **Internet** má hodnotu **AuthenticodeRequired** a **UntrustedSites** má hodnotu **zakázané**.  
  
### <a name="to-enable-the-inclusion-list-programmatically"></a>Chcete-li povolit seznam povolených položek prostřednictvím kódu programu  
  
1.  Vytvoření jazyka Visual Basic nebo Visual C# konzolové aplikace.  
  
2.  Otevřít *soubor Program.vb* nebo *Program.cs* pro úpravy a přidejte následující kód.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Enabled")  
    key.SetValue("LocalIntranet", "Enabled")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "Enabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Enabled");  
    key.SetValue("LocalIntranet", "Enabled");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "Enabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Sestavte a spusťte aplikaci.  
  
## <a name="restrict-the-inclusion-list"></a>Omezte seznam povolených položek  
 Omezte seznam povolených položek, aby řešení musí být podepsány pomocí technologie Authenticode certifikáty, které mají známé identity, než se uživatelům zobrazí výzva rozhodnutí důvěryhodnosti.  
  
### <a name="to-restrict-the-inclusion-list"></a>K omezení seznamu povolených položek  
  
1.  Otevřete editor registru:  
  
    1.  Klikněte na tlačítko **Start**a potom klikněte na tlačítko **spustit**.  
  
    2.  V **otevřít** zadejte **regedt32.exe**a potom klikněte na tlačítko **OK**.  
  
2.  Vyhledejte následující klíč registru:  
  
     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\.NETFramework\Security\TrustManager\PromptingLevel**  
  
     Pokud klíč neexistuje, vytvořte ho.  
  
3.  Přidejte následující podklíče jako **řetězcovou hodnotu**, pokud ještě neexistují, s přiřazenými hodnotami.  
  
    |Hodnota řetězce podklíče|Hodnota|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**Disabled** (Zakázáno)|  
    |**Internet**|**AuthenticodeRequired**|  
    |**MyComputer**|**AuthenticodeRequired**|  
    |**LocalIntranet**|**AuthenticodeRequired**|  
    |**TrustedSites**|**AuthenticodeRequired**|  
  
     Ve výchozím nastavení **Internet** má hodnotu **AuthenticodeRequired** a **UntrustedSites** má hodnotu **zakázané**.  
  
### <a name="to-restrict-the-inclusion-list-programmatically"></a>K omezení seznamu povolených položek prostřednictvím kódu programu  
  
1.  Vytvoření jazyka Visual Basic nebo Visual C# konzolové aplikace.  
  
2.  Otevřít *soubor Program.vb* nebo *Program.cs* pro úpravy a přidejte následující kód.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "AuthenticodeRequired")  
    key.SetValue("LocalIntranet", "AuthenticodeRequired")  
    key.SetValue("Internet", "AuthenticodeRequired")  
    key.SetValue("TrustedSites", "AuthenticodeRequired")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "AuthenticodeRequired");  
    key.SetValue("LocalIntranet", "AuthenticodeRequired");  
    key.SetValue("Internet", "AuthenticodeRequired");  
    key.SetValue("TrustedSites", "AuthenticodeRequired");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
    ```  
  
3.  Sestavte a spusťte aplikaci.  
  
## <a name="disable-the-inclusion-list"></a>Zakázat seznam povolených položek  
 Seznam povolených položek můžete zakázat, aby koncoví uživatelé můžou nainstalovat pouze řešení, které jsou podepsané důvěryhodným a známým certifikátem.  
  
### <a name="to-disable-the-inclusion-list"></a>Chcete-li zakázat seznam povolených položek  
  
1.  Otevřete editor registru:  
  
    1.  Klikněte na tlačítko **Start**a potom klikněte na tlačítko **spustit**.  
  
    2.  V **otevřít** zadejte **regedt32.exe**a potom klikněte na tlačítko **OK**.  
  
2.  Pokud to ještě neexistuje, vytvořte následující klíč registru:  
  
     **\HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\\.NETFramework\Security\TrustManager\PromptingLevel**  
  
3.  Přidejte následující podklíče jako **řetězcovou hodnotu**, pokud ještě neexistují, s přiřazenými hodnotami.  
  
    |Hodnota řetězce podklíče|Hodnota|  
    |-------------------------|-----------|  
    |**UntrustedSites**|**Disabled** (Zakázáno)|  
    |**Internet**|**Disabled** (Zakázáno)|  
    |**MyComputer**|**Disabled** (Zakázáno)|  
    |**LocalIntranet**|**Disabled** (Zakázáno)|  
    |**TrustedSites**|**Disabled** (Zakázáno)|  
  
### <a name="to-disable-the-inclusion-list-programmatically"></a>Chcete-li zakázat seznam povolených položek prostřednictvím kódu programu  
  
1.  Vytvoření jazyka Visual Basic nebo Visual C# konzolové aplikace.  
  
2.  Otevřít *soubor Program.vb* nebo *Program.cs* pro úpravy a přidejte následující kód.  
  
    ```vb  
    Dim key As Microsoft.Win32.RegistryKey  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\MICROSOFT\.NETFramework\Security\TrustManager\PromptingLevel")  
    key.SetValue("MyComputer", "Disabled")  
    key.SetValue("LocalIntranet", "Disabled")  
    key.SetValue("Internet", "Disabled")  
    key.SetValue("TrustedSites", "Disabled")  
    key.SetValue("UntrustedSites", "Disabled")  
    key.Close()  
    ```  
  
    ```csharp  
    Microsoft.Win32.RegistryKey key;  
    key = Microsoft.Win32.Registry.LocalMachine.CreateSubKey("SOFTWARE\\MICROSOFT\\.NETFramework\\Security\\TrustManager\\PromptingLevel");  
    key.SetValue("MyComputer", "Disabled");  
    key.SetValue("LocalIntranet", "Disabled");  
    key.SetValue("Internet", "Disabled");  
    key.SetValue("TrustedSites", "Disabled");  
    key.SetValue("UntrustedSites", "Disabled");  
    key.Close();  
  
    ```  
  
3.  Sestavte a spusťte aplikaci.  
  
## <a name="see-also"></a>Viz také:  
 [Vztah důvěryhodnosti řešení pro systém Office s použitím seznamů povolených položek](../vsto/trusting-office-solutions-by-using-inclusion-lists.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)  
