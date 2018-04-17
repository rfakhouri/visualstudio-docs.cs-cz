---
title: Dotazování. Soubor PDB | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PDB files
- .pdb files, querying
ms.assetid: 8da07d1c-2712-45f9-8fbf-f34040408a8a
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b2f4e6c153cb7f2729e95137c07198858dd4bfa7
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="querying-the-pdb-file"></a>Dotazování na soubor .Pdb
Soubor databáze programu (rozšíření .pdb) je binární soubor, který obsahuje typ a symbolické ladicí informace shromážděné v průběhu kompilace a propojení projektu. Soubor PDB se vytvoří při kompilace programu C/C++ s **/ZI** nebo **/Zi** nebo [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], nebo [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] programu s **/debug** možnost. Soubory objektů obsahují odkazy, do souboru PDB informace o ladění. Další informace o soubory pdb najdete v tématu [soubory PDB](http://msdn.microsoft.com/en-us/1761c84e-8c2c-4632-9649-b5f99964ed3f). DIA aplikace můžete použít následující obecné kroky k získání podrobností o různé symboly, objektů a dat elementů v rámci spustitelné bitové kopie.  
  
### <a name="to-query-the-pdb-file"></a>K dotazování na soubor .pdb  
  
1.  Získat zdroj dat vytvořením [idiadatasource –](../../debugger/debug-interface-access/idiadatasource.md) rozhraní.  
  
    ```C++  
    CComPtr<IDiaDataSource> pSource;  
    hr = CoCreateInstance( CLSID_DiaSource,  
                           NULL,  
                           CLSCTX_INPROC_SERVER,  
                           __uuidof( IDiaDataSource ),  
                          (void **) &pSource);  
  
    if (FAILED(hr))  
    {  
        Fatal("Could not CoCreate CLSID_DiaSource. Register msdia80.dll." );  
    }  
    ```  
  
2.  Volání [idiadatasource::loaddatafrompdb –](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md) nebo [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) načíst informace o ladění.  
  
    ```C++  
    wchar_t wszFilename[ _MAX_PATH ];  
    mbstowcs( wszFilename, szFilename, sizeof( wszFilename )/sizeof( wszFilename[0] ) );  
    if ( FAILED( pSource->loadDataFromPdb( wszFilename ) ) )  
    {  
        if ( FAILED( pSource->loadDataForExe( wszFilename, NULL, NULL ) ) )  
        {  
            Fatal( "loadDataFromPdb/Exe" );  
        }  
    }  
    ```  
  
3.  Volání [idiadatasource::opensession –](../../debugger/debug-interface-access/idiadatasource-opensession.md) otevřete [idiasession –](../../debugger/debug-interface-access/idiasession.md) k získání přístupu k informace o ladění.  
  
    ```C++  
    CComPtr<IDiaSession> psession;  
    if ( FAILED( pSource->openSession( &psession ) ) )   
    {  
        Fatal( "openSession" );  
    }  
    ```  
  
4.  Pomocí metod v nástroji `IDiaSession` dotazu pro symboly v datovém zdroji.  
  
    ```C++  
    CComPtr<IDiaSymbol> pglobal;  
    if ( FAILED( psession->get_globalScope( &pglobal) ) )  
    {  
        Fatal( "get_globalScope" );  
    }  
    ```  
  
5.  Použití `IDiaEnum*` informace o ladění rozhraní k zobrazení výčtu a skenování prostřednictvím symboly nebo další prvky.  
  
    ```C++  
    CComPtr<IDiaEnumTables> pTables;  
    if ( FAILED( psession->getEnumTables( &pTables ) ) )  
    {  
        Fatal( "getEnumTables" );  
    }  
    CComPtr< IDiaTable > pTable;  
    while ( SUCCEEDED( hr = pTables->Next( 1, &pTable, &celt ) ) && celt == 1 )  
    {  
         // Do something with each IDiaTable.  
    }  
    ```  
  
## <a name="see-also"></a>Viz také  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)