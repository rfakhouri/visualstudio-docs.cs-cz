---
title: "Získání seznamu nainstalován fragmenty kódu (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- snippets, retrieving list
- code snippets, retrieving list
- GetSnippets method
ms.assetid: 7d142f8b-35b1-44c4-a13e-f89f6460c906
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 72ebaf6fa64a35982714da67f98c20a287f6caff
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-getting-a-list-of-installed-code-snippets-legacy-implementation"></a>Návod: Získáním seznamu fragmenty kódu nainstalovaný (implementace starší verze)
Fragment kódu je úsek kódu, který lze vložit do zdrojová vyrovnávací paměť s příkazu v nabídce (který umožňuje výběr mezi seznam fragmenty kódu nainstalovaná) nebo pomocí zástupce fragment kódu výběrem ze seznamu doplňování IntelliSense.  
  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionManager.EnumerateExpansions%2A> Metoda získá všechny fragmenty kódu pro konkrétní jazyk identifikátor GUID. Zástupce pro tyto fragmenty lze vložit do dokončení seznam technologie IntelliSense.  
  
 V tématu [podpora fragmenty kódu ve službě jazyk starší](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md) podrobné informace o implementaci fragmenty kódu ve službě spravované balíček framework (MPF) jazyk.  
  
### <a name="to-retrieve-a-list-of-code-snippets"></a>Chcete-li načíst seznam fragmenty kódu  
  
1.  Následující kód ukazuje, jak získat seznam fragmenty kódu pro daný jazyk. Výsledky jsou uloženy v pole <xref:Microsoft.VisualStudio.TextManager.Interop.VsExpansion> struktury. Tato metoda používá statickou <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> metoda získat <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager> rozhraní z <xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager> služby. Ale můžete také použít poskytovatele služeb na VSPackage a volání <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A> metoda.  
  
    ```csharp  
    using System;  
    using System.Collections;  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio.Package;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.TextManager.Interop;  
  
    [Guid("00000000-0000-0000-0000-000000000000")] //create a new GUID for the language service  
    namespace TestLanguage  
    {  
        class TestLanguageService : LanguageService  
        {  
            private void GetSnippets(Guid languageGuid,  
                                     ref ArrayList expansionsList)  
            {  
                IVsTextManager textManager = (IVsTextManager)Package.GetGlobalService(typeof(SVsTextManager));  
                if (textManager != null)  
                {  
                    IVsTextManager2 textManager2 = (IVsTextManager2)textManager;  
                    if (textManager2 != null)  
                    {  
                        IVsExpansionManager expansionManager = null;  
                        textManager2.GetExpansionManager(out expansionManager);  
                        if (expansionManager != null)  
                        {  
                            // Tell the environment to fetch all of our snippets.  
                            IVsExpansionEnumeration expansionEnumerator = null;  
                            expansionManager.EnumerateExpansions(languageGuid,  
                            0,     // return all info  
                            null,    // return all types  
                            0,     // return all types  
                            1,     // include snippets without types  
                            0,     // do not include duplicates  
                            out expansionEnumerator);  
                            if (expansionEnumerator != null)  
                            {  
                                // Cache our expansions in a VsExpansion array   
                                uint count   = 0;  
                                uint fetched = 0;  
                                VsExpansion expansionInfo = new VsExpansion();  
                                IntPtr[] pExpansionInfo   = new IntPtr[1];  
  
                                // Allocate enough memory for one VSExpansion structure. This memory is filled in by the Next method.  
                                pExpansionInfo[0] = Marshal.AllocCoTaskMem(Marshal.SizeOf(expansionInfo));  
  
                                expansionEnumerator.GetCount(out count);  
                                for (uint i = 0; i < count; i++)  
                                {  
                                    expansionEnumerator.Next(1, pExpansionInfo, out fetched);  
                                    if (fetched > 0)  
                                    {  
                                        // Convert the returned blob of data into a structure that can be read in managed code.  
                                        expansionInfo = (VsExpansion)Marshal.PtrToStructure(pExpansionInfo[0], typeof(VsExpansion));  
  
                                        if (!String.IsNullOrEmpty(expansionInfo.shortcut))  
                                        {  
                                            expansionsList.Add(expansionInfo);  
                                        }  
                                    }  
                                }  
                                Marshal.FreeCoTaskMem(pExpansionInfo[0]);  
                            }  
                        }  
                    }  
                }  
            }  
        }  
    }  
    ```  
  
### <a name="to-call-the-getsnippets-method"></a>K volání metody GetSnippets  
  
1.  Následující metodu ukazuje způsob volání `GetSnippets` metoda po dokončení operace analýzy. <xref:Microsoft.VisualStudio.Package.LanguageService.OnParseComplete%2A> Metoda je volána po operaci analýzy, která byla spuštěna s z důvodu <xref:Microsoft.VisualStudio.Package.ParseReason>.  
  
> [!NOTE]
>  `expansionsList` Pole listis uložené v mezipaměti z důvodů výkonu. Změny fragmenty kódu se neprojeví v seznamu, dokud služba jazyka je zastavit a znovu načíst (například podle zastavením a restartováním [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]).  
  
```csharp  
class TestLanguageService : LanguageService  
{  
    private ArrayList expansionsList;  
  
    public override void OnParseComplete(ParseRequest req)  
    {  
        if (this.expansionsList == null)  
        {  
            this.expansionsList = new ArrayList();  
            GetSnippets(this.GetLanguageServiceGuid(),  
                ref this.expansionsList);  
        }  
    }  
}  
```  
  
### <a name="to-use-the-snippet-information"></a>Použití informací fragmentu kódu  
  
1.  Následující kód ukazuje, jak vrácené informace fragmentu kódu `GetSnippets` metoda. `AddSnippets` Metoda je volána z analyzátor v reakci na z jakéhokoli důvodu analýzy, který se používá k naplnění seznamu fragmenty kódu. To by měl proběhnout po první bylo provedeno úplnou analýzu.  
  
     `AddDeclaration` Metoda vytvoří seznam deklarace, později zobrazená v seznamu dokončení.  
  
     `TestDeclaration` Třída obsahuje všechny informace, které lze zobrazit v seznamu dokončení, jakož i typ deklarace.  
  
    ```csharp  
    class TestAuthoringScope : AuthoringScope  
    {  
        public void AddDeclarations(TestDeclaration declaration)  
        {  
            if (m_declarations == null)  
                m_declarations = new List<TestDeclaration>();  
            m_declarations.Add(declaration);  
         }  
    }  
    class TestDeclaration   
    {  
        private string m_name;  
        private string m_description;  
        private string m_type;  
  
        public TestDeclaration(string name, string desc, string type)  
        {  
            m_name = name;  
            m_description = desc;  
            m_type = type;  
        }  
  
    class TestLanguageService : LanguageService  
    {  
        internal void AddSnippets(ref TestAuthoringScope scope)  
        {  
            if (this.expansionsList != null && this.expansionsList.Count > 0)  
            {  
                int count = this.expansionsList.Count;  
                for (int i = 0; i < count; i++)  
                {  
                    VsExpansion expansionInfo = (VsExpansion)this.expansionsList[i];  
                    scope.AddDeclaration(new TestDeclaration(expansionInfo.title,  
                         expansionInfo.description,  
                         "snippet"));  
                }  
            }  
        }  
    }  
  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Podpora pro fragmenty kódu ve službě jazyk starší verze](../../extensibility/internals/support-for-code-snippets-in-a-legacy-language-service.md)