---
title: "Kombinování VBA pro vytváření a úpravy na úrovni dokumentů | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VST.VBAInterop.InvalidAssemblyVersion
- VST.VBAInterop.ProjectLoadFailure
- VST.VBAInterop.MissingGUID
- VST.VBAInterop.EnableComCallers
- VST.VBAInterop.PersistVBACode
- VST.VBAInterop.ReferenceAssemblyFromVBA
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- documents [Office development in Visual Studio], Visual Basic for Applications and
- VBA [Office development in Visual Studio]
- Office documents [Office development in Visual Studio], Visual Basic for Applications and
- VBA [Office development in Visual Studio], about VBA and document-level customizations
- managed code [Office development in Visual Studio], Visual Basic for Applications and
- document-level customizations [Office development in Visual Studio], Visual Basic for Applications and
ms.assetid: 2c10feeb-38af-4802-bbf4-d637db81a884
caps.latest.revision: "36"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: b7dd65878844e5c903b18c08e6dd5455f3dccb91
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="combining-vba-and-document-level-customizations"></a>Kombinování přizpůsobení na úrovních VBA a dokumentu
  Můžete vytvořit jazyka Visual Basic pro aplikace (VBA) kód v dokumentu, který je součástí přizpůsobení na úrovni dokumentu pro aplikace Microsoft Office Word nebo Microsoft Office Excel. VBA kód můžete volat v dokumentu z sestavení vlastní nastavení, nebo můžete nakonfigurovat projekt povolit VBA kód v dokumentu pro volání kódu v sestavení vlastní nastavení.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## <a name="behavior-of-vba-code-in-a-document-level-customization"></a>Chování kódu VBA pro vytváření přizpůsobení na úrovni dokumentu  
 Když otevřete projekt v sadě Visual Studio, dokument se otevře v režimu návrhu. VBA kód nejde spustit, když dokument je v režimu návrhu, abyste mohli pracovat na dokument a kód bez spuštění kódu VBA pro vytváření.  
  
 Když spustíte řešení, obslužné rutiny událostí v VBA pro vytváření a přizpůsobení sestavení odráželo události, které jsou vyvolány v dokumentu, a spusťte obě sady kódu. Nelze určit předem kód, který bude spuštěn před dalších; To je třeba určit prostřednictvím testování v jednotlivých případech. Pokud jsou dvě sady kód není pečlivě koordinované a otestovat, můžete získat neočekávané výsledky.  
  
## <a name="calling-vba-code-from-the-customization-assembly"></a>Volání kódu VBA z přizpůsobení sestavení  
 Makra můžete volat v dokumentech aplikace Word a sešitů aplikace Excel můžete volat makra a funkce. K tomuto účelu použijte jednu z následujících metod:  
  
-   Pro Word, volání <xref:Microsoft.Office.Interop.Word._Application.Run%2A>metodu <xref:Microsoft.Office.Interop.Word.Application> třídy.  
  
-   Pro aplikaci Excel, volání <xref:Microsoft.Office.Interop.Excel._Application.Run%2A> metodu <xref:Microsoft.Office.Interop.Excel.Application> třídy.  
  
 Pro každou metodu první parametr určuje název makro nebo funkce, kterou chcete volat a zbývající volitelné parametry zadejte parametry, které mají být předány makro nebo funkce. První parametr může mít různých formátech pro Word a Excel:  
  
-   První parametr pro Word, je řetězec, který může být libovolnou kombinací šablony, modulu a název makra. Pokud zadáte název dokumentu, kód můžete spustit pouze makra v dokumentech související s aktuálním kontextu – Ne všem makro v dokumentu.  
  
-   Pro aplikaci Excel, první parametr může být řetězec, který určuje název makra <xref:Microsoft.Office.Interop.Excel.Range> určující, kde je funkce nebo ID registrace pro registrovaná funkce DLL (XLL). Pokud předáte řetězec, řetězec bude vyhodnocena v souvislosti s aktivním listem.  
  
 Následující příklad kódu ukazuje, jak volat makro s názvem `MyMacro` z projektu úrovni dokumentu pro Excel. Tento příklad předpokládá, že `MyMacro` je definována v `Sheet1`.  
  
```vb  
Globals.Sheet1.Application.Run("MyMacro")  
```  
  
```csharp  
Globals.Sheet1.Application.Run("MyMacro", missing, missing, missing,  
    missing, missing, missing, missing, missing, missing, missing,  
    missing, missing, missing, missing, missing, missing, missing,  
    missing, missing, missing, missing, missing, missing, missing,   
    missing, missing, missing, missing, missing, missing);  
```  
  
> [!NOTE]  
>  Informace o použití na globální `missing` najdete v části proměnná místo volitelné parametry v jazyce Visual C# [psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md).  
  
## <a name="calling-code-in-document-level-customizations-from-vba"></a>Volání kódu v přizpůsobeních na úrovni dokumentu z jazyka VBA  
 Projekt na úrovni dokumentu pro Word či Excel můžete nakonfigurovat tak, že kódu Visual Basic for Applications (VBA) v dokumentu můžete volat kód v sestavení vlastní nastavení. To je užitečné v následujících scénářích:  
  
-   Chcete rozšířit existující VBA kód v dokumentu pomocí funkcí v přizpůsobení na úrovni dokumentu, který je přidružen ke stejnému dokumentu.  
  
-   Chcete zpřístupnit služby, které vyvíjíte v přizpůsobení na úrovni dokumentu pro koncové uživatele, kteří mohou přístup ke službám pomocí psaní kódu jazyka VBA v dokumentu.  
  
 Nástroje pro vývoj pro Office v sadě Visual Studio poskytují podobné funkce pro doplňky VSTO. Pokud vyvíjíte doplňku VSTO, můžete volat kódu v doplňku VSTO z jiných řešení pro Microsoft Office. Další informace najdete v tématu [volání kódu v doplňcích VSTO z jiných řešení pro systém Office](../vsto/calling-code-in-vsto-add-ins-from-other-office-solutions.md).  
  
> [!NOTE]  
>  Tuto funkci nelze použít v šabloně projekty aplikace Word. Může sloužit pouze v dokument aplikace Word, sešit aplikace Excel nebo projekty šablony aplikace Excel.  
  
## <a name="requirements"></a>Požadavky  
 Před povolením VBA kód provést volání do přizpůsobení sestavení projektu musí splňovat následující požadavky:  
  
-   V dokumentu musí mít jednu z následujících přípon souborů:  
  
    -   Pro aplikaci Word: DOCM nebo .doc  
  
    -   Pro aplikaci Excel: .xlsm, XLTM, XLS nebo xlt  
  
-   Dokument musí obsahovat již VBA projekt, který se nachází VBA kód.  
  
-   VBA kód v dokumentu musí být povoleno spouštět bez výzvy pro uživatele, povolit makra. VBA kód pro spuštění přidáním umístění Microsoft Office project do seznamu důvěryhodných lokalit v nastavení Centrum zabezpečení pro Word či Excel můžete důvěřovat.  
  
-   Microsoft Office project musí obsahovat alespoň jednu veřejnou třídu, která obsahuje jeden nebo více veřejné členy, které jsou vystaveny pro jazyk VBA.  
  
     Můžete vystavit metody, vlastnosti a události pro jazyk VBA. Třída, která vystavit může být třídu položky hostitele (například `ThisDocument` pro Word, nebo `ThisWorkbook` a `Sheet1` pro aplikaci Excel) nebo jiné třídy, která definujete ve vašem projektu. Další informace o hostitelských položkách najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md).  
  
## <a name="enabling-vba-code-to-call-into-the-customization-assembly"></a>Povolení k volání do sestavení přizpůsobení VBA kód  
 Existují dva různé způsoby, můžete vystavit členy v sestavení přizpůsobení VBA kód v dokumentu:  
  
-   Můžou zpřístupnit členy třídy položky hostitele v [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] projekt VBA pro vytváření. Chcete-li to provést, nastavte **EnableVbaCallers** vlastnosti položky hostitele k **True** v **vlastnosti** je okno při hostitelská položka (to znamená, dokument, listu nebo sešitu) Otevřít v návrháři. Visual Studio automaticky provede všechny práce potřebné k povolení VBA kód volat členové třídy.  
  
-   Můžou zpřístupnit členy v jakékoli veřejnou třídu v projektu jazyka Visual C# nebo členy v jiných hostitelů položky třídy v [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] projektu pro jazyk VBA. Tato možnost vám poskytne dává větší svobodu při vyberte třídy, které můžete zpřístupnit pro jazyk VBA, ale také budete potřebovat další ruční kroky.  
  
     Chcete-li to provést, musíte provést následující hlavní kroky:  
  
    1.  Vystavení třídu modelu COM.  
  
    2.  Přepsání **GetAutomationObject** metoda třídy položky hostitele ve vašem projektu a vrátit instanci třídy, která jsou vystavení pro jazyk VBA.  
  
    3.  Nastavte **ReferenceAssemblyFromVbaProject** vlastnost třídy položky všechny hostitele v projektu na **True**. To vloží knihovny typů přizpůsobení sestavení do sestavení a přidá odkaz na knihovnu typů projektu VBA v dokumentu.  
  
 Podrobné pokyny najdete v tématu [postupy: vystavení kódu do VBA v projektu jazyka Visual Basic](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md) a [postupy: vystavení kódu do VBA v Visual C &#35; Projekt](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md).  
  
 **EnableVbaCallers** a **ReferenceAssemblyFromVbaProject** vlastnosti jsou k dispozici pouze v **vlastnosti** okno v době návrhu; nelze je použít za běhu . Chcete-li zobrazit vlastnosti, otevřete návrháře pro položku hostitele v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Další informace o konkrétní úlohy, které Visual Studio provádí při nastavení těchto vlastností najdete v tématu [úlohy prováděné vlastnosti položky hostitele](#PropertyTasks).  
  
> [!NOTE]  
>  Pokud sešit nebo dokument už neobsahuje VBA kód nebo pokud VBA kód v dokumentu není důvěryhodný pro spuštění, zobrazí se chybová zpráva při nastavení **EnableVbaCallers** nebo **ReferenceAssemblyFromVbaProject**  vlastnost **True**. Je to proto, že Visual Studio nelze změnit na projekt VBA v dokumentu v této situaci.  
  
## <a name="using-members-in-vba-code-to-call-into-the-customization-assembly"></a>Používání členů v kódu jazyka VBA provést volání do přizpůsobení sestavení  
 Po dokončení konfigurace projektu povolit VBA kód provést volání do sestavení přizpůsobení, Visual Studio přidá následující členy do projektu VBA v dokumentu:  
  
-   U všech projektů sady Visual Studio přidá globální metodu s názvem `GetManagedClass`.  
  
-   Pro [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] projekty, ve kterých vystavit členy hostitele položky třídy pomocí **EnableVbaCallers** vlastnost, Visual Studio také přidá vlastnost s názvem `CallVSTOAssembly` k `ThisDocument`, `ThisWorkbook`, `Sheet1`, `Sheet2`, nebo `Sheet3` modulu v projektu VBA pro vytváření.  
  
 Můžete použít `CallVSTOAssembly` vlastnost nebo `GetManagedClass` metoda pro přístup k veřejné členy třídy, která vystaveni kódu jazyka VBA v projektu.  
  
> [!NOTE]  
>  Při vývoji a nasazení řešení, je několik různých kopií dokumentu kterém můžete přidat VBA kód. Další informace najdete v tématu [pokyny pro přidání kódu jazyka VBA v dokumentu](#Guidelines).  
  
### <a name="using-the-callvstoassembly-property-in-a-visual-basic-project"></a>Pomocí vlastnosti CallVSTOAssembly v projektu jazyka Visual Basic  
 Použití `CallVSTOAssembly` vlastnost, která má přístup k veřejné členy, které jste přidali do položky třída hostitele. Například následující makro VBA volá metodu s názvem `MyVSTOMethod` definovaný v `Sheet1` – třída v projektu sešitu aplikace Excel.  
  
```  
Sub MyMacro()  
    Sheet1.CallVSTOAssembly.MyVSTOMethod()  
End Sub  
```  
  
 Tato vlastnost je pohodlnější způsob, jak provádět volání do sestavení přizpůsobení než při použití `GetManagedClass` metoda přímo. `CallVSTOAssembly`Vrátí objekt, který představuje hostitele pro jazyk VBA třída položek, který je zveřejněný. Členy a parametry metody vráceného objektu se zobrazí v technologii IntelliSense.  
  
 `CallVSTOAssembly` Vlastnost obsahuje deklaraci, která je podobná následující kód. Tento kód předpokládá, že máte vystavení `Sheet1` třída položky v projektu sešitu aplikace Excel s názvem hostitele `ExcelWorkbook1` pro jazyk VBA.  
  
```  
Property Get CallVSTOAssembly() As ExcelWorkbook1.Sheet1  
    Set CallVSTOAssembly = GetManagedClass(Me)  
End Property  
```  
  
### <a name="using-the-getmanagedclass-method"></a>Pomocí metody GetManagedClass  
 Použít na globální `GetManagedClass` metoda, předejte jí objekt VBA pro vytváření, která odpovídá k třídě položky hostitele, který obsahuje přepsání služby **GetAutomationObject** metoda. Pro přístup třídu, která vystavený pro jazyk VBA pak použijte vráceného objektu.  
  
 Například následující makro VBA volá metodu s názvem `MyVSTOMethod` definovaný v `Sheet1` třída položky v projektu sešitu aplikace Excel s názvem hostitele `ExcelWorkbook1`.  
  
```  
Sub CallVSTOMethod  
    Dim VSTOSheet1 As ExcelWorkbook1.Sheet1  
    Set VSTOSheet1 = GetManagedClass(Sheet1)  
    VSTOSheet1.MyVSTOMethod  
End Sub  
```  
  
 `GetManagedClass` Metoda má následující prohlášení.  
  
```  
GetManagedClass(pdispInteropObject Object) As Object  
```  
  
 Tato metoda vrátí objekt, který představuje třídu, která je vystavený pro jazyk VBA. Členy a parametry metody vráceného objektu se zobrazí v technologii IntelliSense.  
  
##  <a name="Guidelines"></a>Pokyny pro přidání VBA kód do dokumentu  
 Existuje několik různých kopie dokumentu kterém můžete přidat VBA kód, který volá do přizpůsobení na úrovni dokumentu.  
  
 Při vývoji a testování řešení, můžete napsat kód VBA v dokumentu, které se otevře při ladění a spustit projekt v sadě Visual Studio (tedy dokumentu v zadané výstupní složce sestavení). Ale kód jazyka VBA, které přidáte k tomuto dokumentu budou přepsány příštím sestavení projektu, protože Visual Studio nahradí kopii dokumentu ze složky hlavní projektu dokumentu do výstupní složky sestavení.  
  
 Pokud chcete uložit VBA kód, který přidáte do dokumentu při ladění nebo řešení spuštěna, zkopírujte kód VBA do dokumentu ve složce projektu. Další informace o procesu sestavení najdete v tématu [vytváření řešení pro systém Office](../vsto/building-office-solutions.md).  
  
 Jakmile budete připraveni k nasazení řešení, existují tři hlavní dokumentu umístění, ve které můžete přidat VBA kód.  
  
### <a name="in-the-project-folder-on-the-development-computer"></a>Ve složce projektu na vývojovém počítači  
 Toto umístění je vhodné, pokud máte plnou kontrolu nad VBA kód v dokumentu a kód vlastní nastavení. Vzhledem k tomu, že je na vývojovém počítači, můžete snadno upravit VBA kód, pokud změníte kód vlastní nastavení. VBA kód, který přidáte do této kopie dokumentu zůstane v dokumentu, při sestavování, ladění a publikování řešení.  
  
 VBA kód nelze přidat k dokumentu je otevřen v návrháři. Musíte nejdřív zavřete dokument v návrháři a pak otevřete dokument přímo v Word či Excel.  
  
> [!CAUTION]  
>  Pokud přidáte VBA kód, který je spuštěn při otevření dokumentu, ve výjimečných případech tento kód může být poškozený dokumentu nebo zabránit jeho otevření v návrháři.  
  
### <a name="in-the-publish-or-installation-folder"></a>Ve složce instalace nebo publikování  
 V některých případech může být vhodné přidat kód VBA v dokumentu ve složce instalace nebo publikování. Například můžete zvolit tuto možnost, pokud je kód VBA vytvoření a otestování jiný vývojář na počítači, který nemá nainstalovanou sadu Visual Studio.  
  
 Pokud uživatelé nainstalují řešení přímo ve složce publikovat, je nutné přidat kód VBA v dokumentu pokaždé, když publikujete řešení. Visual Studio přepíše dokumentu v umístění pro publikování, při publikování řešení.  
  
 Pokud uživatelé nainstalují řešení z instalační složky, které se liší od složce publikování, se můžete vyhnout přidávání kódu jazyka VBA v dokumentu pokaždé, když publikujete řešení. Při publikování aktualizace je připraven k přesunování ze složky publikovat do složky pro instalaci, zkopírujte všechny soubory do složky pro instalaci s výjimkou dokumentu.  
  
### <a name="on-the-end-user-computer"></a>Na počítači koncového uživatele  
 Pokud koncoví uživatelé jsou VBA vývojáře, kteří jsou volání do služby, které zadáte v přizpůsobení na úrovni dokumentu, můžete zadat, je způsob, jak volat kódu pomocí `CallVSTOAssembly` vlastnost nebo `GetManagedClass` metoda v jejich kopie dokumentu. Při publikování aktualizace řešení VBA kód v dokumentu na počítači koncového uživatele nedojde k přepsání, protože není upraveny dokumentu publikovat aktualizace.  
  
##  <a name="PropertyTasks"></a>Úlohy prováděné vlastnosti položky hostitele  
 Při použití **EnableVbaCallers** a **ReferenceAssemblyFromVbaProject** vlastnosti, Visual Studio provádí různé skupiny úloh.  
  
### <a name="enablevbacallers"></a>EnableVbaCallers  
 Když nastavíte **EnableVbaCallers** vlastnosti hostitele položky k **True** v projektu jazyka Visual Basic, Visual Studio provádí následující úlohy:  
  
1.  Přidá <xref:Microsoft.VisualBasic.ComClassAttribute> a <xref:System.Runtime.InteropServices.ComVisibleAttribute> atributy pro třídu položky hostitele.  
  
2.  Přepíše **GetAutomationObject** metoda třídy položky hostitele.  
  
3.  Nastaví **ReferenceAssemblyFromVbaProject** vlastnosti položky hostitele k **True**.  
  
 Když nastavíte **EnableVbaCallers** vlastnost zpět do **False**, Visual Studio provádí následující úlohy:  
  
1.  Odebere <xref:Microsoft.VisualBasic.ComClassAttribute> a <xref:System.Runtime.InteropServices.ComVisibleAttribute> atributy z `ThisDocument` třídy.  
  
2.  Odebere **GetAutomationObject** metoda z položky třída hostitele.  
  
    > [!NOTE]  
    >  Visual Studio automaticky nenastaví **ReferenceAssemblyFromVbaProject** vlastnost zpět do **False**. Tuto vlastnost lze nastavit **False** ručně pomocí **vlastnosti** okno.  
  
### <a name="referenceassemblyfromvbaproject"></a>ReferenceAssemblyFromVbaProject  
 Když **ReferenceAssemblyFromVbaProject** položky všechny hostitele v projektu jazyka Visual Basic a Visual C# je nastavena na **True**, Visual Studio provádí následující úlohy:  
  
1.  Generuje knihovny typů pro přizpůsobení sestavení a vloží knihovny typů v sestavení.  
  
2.  Přidá odkaz na následující knihovny typů v projektu jazyka VBA v dokumentu:  
  
    -   Knihovny typů pro vaše vlastní nastavení sestavení.  
  
    -   Sady Microsoft Visual Studio Tools for Office provádění modul 9.0 knihovny typů. Je součástí této knihovny typů [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
 Když **ReferenceAssemblyFromVbaProject** vlastnost se nastaví zpátky na **False**, Visual Studio provádí následující úlohy:  
  
1.  Odkazy na typu knihovny se odeberou z projektu VBA v dokumentu.  
  
2.  Odebere knihovně vloženého typu ze sestavení.  
  
## <a name="troubleshooting"></a>Poradce při potížích  
 Následující tabulka uvádí některé běžné chyby a návrhy řešení chyb.  
  
|Chyba|Návrh|  
|-----------|----------------|  
|Jakmile nastavíte **EnableVbaCallers** nebo **ReferenceAssemblyFromVbaProject** vlastnost chybovou zprávu stavy dokument neobsahuje projekt VBA, nebo nemáte oprávnění k přístupu Projekt VBA v dokumentu.|Zajistěte, aby dokument v projektu obsahuje alespoň jeden makro VBA pro vytváření, projekt VBA má dostatečná vztah důvěryhodnosti ke spuštění a projekt VBA není chráněn heslem.|  
|Po nastavení **EnableVbaCallers** nebo **ReferenceAssemblyFromVbaProject** vlastnost, chybová zpráva uvádí, že <xref:System.Runtime.InteropServices.GuidAttribute> deklarace je chybějící nebo poškozené.|Ujistěte se, že <xref:System.Runtime.InteropServices.GuidAttribute> deklarace se nachází v souboru AssemblyInfo.cs nebo AssemblyInfo.vb ve vašem projektu a že tento atribut je nastaven na platný identifikátor GUID.|  
|Jakmile nastavíte **EnableVbaCallers** nebo **ReferenceAssemblyFromVbaProject** stavy chybovou zprávu vlastnost, že číslo verze určeného <xref:System.Reflection.AssemblyVersionAttribute> není platný.|Ujistěte se, že <xref:System.Reflection.AssemblyVersionAttribute> deklarace v souboru AssemblyInfo.cs nebo AssemblyInfo.vb ve vašem projektu nastavena na číslo verze sestavení platný. Informace o platné sestavení čísla verzí, najdete v článku <xref:System.Reflection.AssemblyVersionAttribute> třídy.|  
|Po přejmenování přizpůsobení sestavení VBA kód, který volá do sestavení přizpůsobení přestane fungovat.|Pokud změníte název sestavení, přizpůsobení po zveřejnění VBA kód, dojde k přerušení propojení mezi projekt VBA v dokumentu a vaše přizpůsobení sestavení. Chcete-li tento problém vyřešit, změňte **ReferenceFromVbaAssembly** vlastnost ve vašem projektu a **False** a pak zpátky na **True**a potom můžete nahradit všechny odkazy na staré sestavení název v VBA kód s novým názvem sestavení.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: vystavení kódu do VBA v projektu jazyka Visual Basic](../vsto/how-to-expose-code-to-vba-in-a-visual-basic-project.md)   
 [Postupy: vystavení kódu do VBA v Visual C &#35; Projekt](../vsto/how-to-expose-code-to-vba-in-a-visual-csharp-project.md)   
 [Návod: Volání kódu z jazyka VBA v projektu jazyka Visual Basic](../vsto/walkthrough-calling-code-from-vba-in-a-visual-basic-project.md)   
 [Návod: Volání kódu z jazyka VBA v Visual C &#35; Projekt](../vsto/walkthrough-calling-code-from-vba-in-a-visual-csharp-project.md)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [VBA a řešení pro systém Office v sadě Visual Studio porovnání](../vsto/vba-and-office-solutions-in-visual-studio-compared.md)   
 [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)  
  
  