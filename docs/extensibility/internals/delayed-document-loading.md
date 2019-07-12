---
title: Odložené načtení dokumentu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: fb07b8e2-a4e3-4cb0-b04f-8eb11c491f35
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 30a3b1ce88a3e6a8069053c6d9daa14230034b28
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67821826"
---
# <a name="delayed-document-loading"></a>Odložené načtení dokumentu

Když uživatel otevře řešení sady Visual Studio, nejsou načtené okamžitě většinu související dokumenty. Rámeček okna dokumentu se vytvoří ve stavu čekající na inicializaci a zástupný symbol dokumentu (označované jako rámce se zakázaným inzerováním) je umístěn v tabulce spuštění dokumentu (r...).

Rozšíření může způsobit, že dokumenty projektu zbytečně načíst pomocí dotazu na prvky v dokumentech před jejich načtení, které může zvýšit celkový objem paměti pro sadu Visual Studio.

## <a name="document-loading"></a>Načtení dokumentu

Zástupná procedura rámce a dokument se plně inicializován při přístupu uživatele k dokumentu, třeba tak, že vyberete kartu rámec okna. Dokument může být navíc inicializované rozšíření, který vyžaduje data dokumentu, buď si přístup k rámcový přímo k získání dat dokumentu nebo přejdou rámcový nepřímo tím, že jeden následující volání:

- Snímek okna <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> metody.

- Snímek okna <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> metodu na některý z následujících vlastností:

  - [__VSFPROPID.VSFPROPID_DocView](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_DocView>)

  - [__VSFPROPID.VSFPROPID_ViewHelper](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_ViewHelper>)

  - [__VSFPROPID.VSFPROPID_DocData](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_DocData>)

  - [__VSFPROPID.VSFPROPID_AltDocData](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_AltDocData>)

  - [__VSFPROPID.VSFPROPID_RDTDocData](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_RDTDocData>)

  - [__VSFPROPID.VSFPROPID_SPProjContext](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID.VSFPROPID_SPProjContext>)

- Pokud rozšíření používá spravovaný kód, neměli by jste volat <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> Pokud si nejste jisti, že dokument není ve stavu čekající na inicializaci, nebo chcete dokument, aby se plně inicializovat. Důvodem je, protože metoda vždy vrátí dokumentu datový objekt, v případě potřeby jeho vytvoření. Místo toho byste měli volat jednu z metod na `IVsRunningDocumentTable4` rozhraní.

- Pokud rozšíření používá C++, můžete předat `null` parametrů nechcete.

- Vyhnete zbytečným dokumentu načítání voláním jedné z následujících metod předtím, než můžete požádat o příslušné vlastnosti před požádat o další vlastnosti:

  - <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> pomocí [__VSFPROPID6. VSFPROPID_PendingInitialization](<xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID6.VSFPROPID_PendingInitialization>).

  - <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A>. Tato metoda vrátí hodnotu <xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4> objekt, který obsahuje hodnotu pro [_VSRDTFLAGS4. RDT_PendingInitialization](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4.RDT_PendingInitialization>) Pokud dokument ještě nebyl inicializován.

Můžete zjistit po načtení dokumentu prostřednictvím přihlášení odběru rámcový událost, která se vyvolá, když je dokument plně inicializován. Existují dvě možnosti:

- Pokud se implementuje jímky událostí <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2>, můžete přihlásit k odběru <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents2.OnAfterAttributeChangeEx%2A>,

- V opačném případě k odběru <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocTableEvents.OnAfterAttributeChange%2A>.

V následujícím příkladu je scénář přístupu hypotetické dokumentu: Chce zobrazit některé informace o otevřených dokumentů rozšíření sady Visual Studio, například úpravu zamykací počet a něco o data dokumentu. Vypíše dokumenty v r... pomocí <xref:Microsoft.VisualStudio.Shell.Interop.IEnumRunningDocuments>, pak zavolá <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable.GetDocumentInfo%2A> pro každý dokument, aby bylo možné načíst data upravit zámek počet a dokumentu. Pokud je ve stavu čekající inicializace, žádosti o data dokumentu způsobí zbytečně inicializovat.

Efektivnější způsob přístupu k dokumentu je použití <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentEditLockCount%2A> získat počet zámků úpravy a pak použít <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentFlags%2A> k určení, zda byl inicializován dokumentu. Pokud neobsahují příznaky [_VSRDTFLAGS4. RDT_PendingInitialization](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4.RDT_PendingInitialization>), dokument už je inicializovaný, oznamovat data dokumentu s <xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable4.GetDocumentData%2A> nezpůsobí žádné zbytečné inicializace. Pokud obsahovat příznaky [_VSRDTFLAGS4. RDT_PendingInitialization](<xref:Microsoft.VisualStudio.Shell.Interop._VSRDTFLAGS4.RDT_PendingInitialization>), rozšíření se měli vyhnout vyžadující data dokumentu, dokud je inicializován dokumentu. Tato inicializace lze zjistit v `OnAfterAttributeChange(Ex)` obslužné rutiny události.

## <a name="test-extensions-to-see-if-they-force-initialization"></a>Testování rozšíření, pokud chcete zobrazit, pokud se inicializace vynucení

Neexistuje žádná viditelná startovací označující, zda byl inicializován dokumentu, tak může být obtížné zjistit, pokud je vaše rozšíření vynucení inicializace. Můžete nastavit klíč registru, který usnadňuje ověření, protože způsobuje, že název každého dokumentu, který nebyl plně inicializován tak, že text *[Stub]* v názvu.

V **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\14.0\BackgroundSolutionLoad**, nastavte **StubTabTitleFormatString** k  *{0} [Stub]* .
