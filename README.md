# Supermarket-inventory-management-system

#include "stdafx.h"
#include "_recordset.h"
#include "properties.h"
#include "fields.h"

CProperties C_Recordset::GetProperties()

{

	LPDISPATCH pDispatch;
	InvokeHelper(0x1f4, DISPATCH_PROPERTYGET, VT_DISPATCH, (void*)&pDispatch, NULL);
	return CProperties(pDispatch);
}

long C_Recordset::GetAbsolutePosition()

{

	long result;
	InvokeHelper(0x3e8, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetAbsolutePosition(long nNewValue)

{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x3e8, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 nNewValue);
}

void C_Recordset::SetRefActiveConnection(LPDISPATCH newValue)

{

	static BYTE parms[] =
		VTS_DISPATCH;
	InvokeHelper(0x3e9, DISPATCH_PROPERTYPUTREF, VT_EMPTY, NULL, parms,
		 newValue);
}

void C_Recordset::SetActiveConnection(const VARIANT& newValue)

{

	static BYTE parms[] =
		VTS_VARIANT;
	InvokeHelper(0x3e9, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 &newValue);
}

VARIANT C_Recordset::GetActiveConnection()

{

	VARIANT result;
	InvokeHelper(0x3e9, DISPATCH_PROPERTYGET, VT_VARIANT, (void*)&result, NULL);
	return result;
}

BOOL C_Recordset::GetBof()
{

	BOOL result;
	InvokeHelper(0x3ea, DISPATCH_PROPERTYGET, VT_BOOL, (void*)&result, NULL);
	return result;
}

VARIANT C_Recordset::GetBookmark()
{

	VARIANT result;
	InvokeHelper(0x3eb, DISPATCH_PROPERTYGET, VT_VARIANT, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetBookmark(const VARIANT& newValue)
{

	static BYTE parms[] =
		VTS_VARIANT;
	InvokeHelper(0x3eb, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 &newValue);
}

long C_Recordset::GetCacheSize()
{

	long result;
	InvokeHelper(0x3ec, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetCacheSize(long nNewValue)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x3ec, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 nNewValue);
}

long C_Recordset::GetCursorType()
{

	long result;
	InvokeHelper(0x3ed, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetCursorType(long nNewValue)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x3ed, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 nNewValue);
}

BOOL C_Recordset::GetEof()
{

	BOOL result;
	InvokeHelper(0x3ee, DISPATCH_PROPERTYGET, VT_BOOL, (void*)&result, NULL);
	return result;
}

CFields C_Recordset::GetFields()
{

	LPDISPATCH pDispatch;
	InvokeHelper(0x0, DISPATCH_PROPERTYGET, VT_DISPATCH, (void*)&pDispatch, NULL);
	return CFields(pDispatch);
}

long C_Recordset::GetLockType()
{

	long result;
	InvokeHelper(0x3f0, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetLockType(long nNewValue)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x3f0, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 nNewValue);
}

long C_Recordset::GetMaxRecords()
{
	
	long result;
	InvokeHelper(0x3f1, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetMaxRecords(long nNewValue)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x3f1, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 nNewValue);
}

long C_Recordset::GetRecordCount()
{
	
	long result;
	InvokeHelper(0x3f2, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetRefSource(LPDISPATCH newValue)
{

	static BYTE parms[] =
		VTS_DISPATCH;
	InvokeHelper(0x3f3, DISPATCH_PROPERTYPUTREF, VT_EMPTY, NULL, parms,
		 newValue);
}

void C_Recordset::SetSource(LPCTSTR lpszNewValue)
{

	static BYTE parms[] =
		VTS_BSTR;
	InvokeHelper(0x3f3, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 lpszNewValue);
}

VARIANT C_Recordset::GetSource()
{

	VARIANT result;
	InvokeHelper(0x3f3, DISPATCH_PROPERTYGET, VT_VARIANT, (void*)&result, NULL);
	return result;
}

void C_Recordset::AddNew(const VARIANT& FieldList, const VARIANT& Values)
{

	static BYTE parms[] =
		VTS_VARIANT VTS_VARIANT;
	InvokeHelper(0x3f4, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 &FieldList, &Values);
}

void C_Recordset::CancelUpdate()
{

	InvokeHelper(0x3f5, DISPATCH_METHOD, VT_EMPTY, NULL, NULL);
}

void C_Recordset::Close()
{

	InvokeHelper(0x3f6, DISPATCH_METHOD, VT_EMPTY, NULL, NULL);
}

void C_Recordset::Delete(long AffectRecords)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x3f7, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 AffectRecords);
}

VARIANT C_Recordset::GetRows(long Rows, const VARIANT& Start, const VARIANT& Fields)
{

	VARIANT result;
	static BYTE parms[] =
		VTS_I4 VTS_VARIANT VTS_VARIANT;
	InvokeHelper(0x3f8, DISPATCH_METHOD, VT_VARIANT, (void*)&result, parms,
		Rows, &Start, &Fields);
	return result;
}

void C_Recordset::Move(long NumRecords, const VARIANT& Start)
{

	static BYTE parms[] =
		VTS_I4 VTS_VARIANT;
	InvokeHelper(0x3f9, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 NumRecords, &Start);
}

void C_Recordset::MoveNext()
{

	InvokeHelper(0x3fa, DISPATCH_METHOD, VT_EMPTY, NULL, NULL);
}

void C_Recordset::MovePrevious()
{
	InvokeHelper(0x3fb, DISPATCH_METHOD, VT_EMPTY, NULL, NULL);
}

void C_Recordset::MoveFirst()
{

	InvokeHelper(0x3fc, DISPATCH_METHOD, VT_EMPTY, NULL, NULL);
}

void C_Recordset::MoveLast()
{
	InvokeHelper(0x3fd, DISPATCH_METHOD, VT_EMPTY, NULL, NULL);
}

void C_Recordset::Open(const VARIANT& Source, const VARIANT& ActiveConnection, long CursorType, long LockType, long Options)
{

	static BYTE parms[] =
		VTS_VARIANT VTS_VARIANT VTS_I4 VTS_I4 VTS_I4;
	InvokeHelper(0x3fe, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 &Source, &ActiveConnection, CursorType, LockType, Options);
}

void C_Recordset::Requery(long Options)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x3ff, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 Options);
}

void C_Recordset::Update(const VARIANT& Fields, const VARIANT& Values)
{
	
	static BYTE parms[] =
		VTS_VARIANT VTS_VARIANT;
	InvokeHelper(0x401, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 &Fields, &Values);
}

long C_Recordset::GetAbsolutePage()
{

	long result;
	InvokeHelper(0x417, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetAbsolutePage(long nNewValue)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x417, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 nNewValue);
}

long C_Recordset::GetEditMode()
{
	
	long result;
	InvokeHelper(0x402, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

VARIANT C_Recordset::GetFilter()
{

	VARIANT result;
	InvokeHelper(0x406, DISPATCH_PROPERTYGET, VT_VARIANT, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetFilter(const VARIANT& newValue)
{

	static BYTE parms[] =
		VTS_VARIANT;
	InvokeHelper(0x406, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 &newValue);
}

long C_Recordset::GetPageCount()
{

	long result;
	InvokeHelper(0x41a, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

long C_Recordset::GetPageSize()
{

	long result;
	InvokeHelper(0x418, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetPageSize(long nNewValue)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x418, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 nNewValue);
}

CString C_Recordset::GetSort()
{

	CString result;
	InvokeHelper(0x407, DISPATCH_PROPERTYGET, VT_BSTR, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetSort(LPCTSTR lpszNewValue)
{

	static BYTE parms[] =
		VTS_BSTR;
	InvokeHelper(0x407, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 lpszNewValue);
}

long C_Recordset::GetStatus()
{

	long result;
	InvokeHelper(0x405, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

long C_Recordset::GetState()
{

	long result;
	InvokeHelper(0x41e, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::UpdateBatch(long AffectRecords)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x40b, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 AffectRecords);
}

void C_Recordset::CancelBatch(long AffectRecords)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x419, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 AffectRecords);
}

long C_Recordset::GetCursorLocation()
{

	long result;
	InvokeHelper(0x41b, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetCursorLocation(long nNewValue)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x41b, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 nNewValue);
}

C_Recordset C_Recordset::NextRecordset(VARIANT* RecordsAffected)
{

	LPDISPATCH pDispatch;
	static BYTE parms[] =
		VTS_PVARIANT;
	InvokeHelper(0x41c, DISPATCH_METHOD, VT_DISPATCH, (void*)&pDispatch, parms,
		RecordsAffected);
	return C_Recordset(pDispatch);
}

BOOL C_Recordset::Supports(long CursorOptions)
{

	BOOL result;
	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x40c, DISPATCH_METHOD, VT_BOOL, (void*)&result, parms,
		CursorOptions);
	return result;
}

long C_Recordset::GetMarshalOptions()
{

	long result;
	InvokeHelper(0x41d, DISPATCH_PROPERTYGET, VT_I4, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetMarshalOptions(long nNewValue)
{

	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x41d, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 nNewValue);
}

void C_Recordset::Find(LPCTSTR Criteria, long SkipRecords, long SearchDirection, const VARIANT& Start)
{

	static BYTE parms[] =
		VTS_BSTR VTS_I4 VTS_I4 VTS_VARIANT;
	InvokeHelper(0x422, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 Criteria, SkipRecords, SearchDirection, &Start);
}

void C_Recordset::Cancel()
{

	InvokeHelper(0x41f, DISPATCH_METHOD, VT_EMPTY, NULL, NULL);
}

LPUNKNOWN C_Recordset::GetDataSource()
{

	LPUNKNOWN result;
	InvokeHelper(0x420, DISPATCH_PROPERTYGET, VT_UNKNOWN, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetRefDataSource(LPUNKNOWN newValue)
{

	static BYTE parms[] =
		VTS_UNKNOWN;
	InvokeHelper(0x420, DISPATCH_PROPERTYPUTREF, VT_EMPTY, NULL, parms,
		 newValue);
}

void C_Recordset::Save(LPCTSTR FileName, long PersistFormat)
{

	static BYTE parms[] =
		VTS_BSTR VTS_I4;
	InvokeHelper(0x421, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 FileName, PersistFormat);
}

LPDISPATCH C_Recordset::GetActiveCommand()
{

	LPDISPATCH result;
	InvokeHelper(0x425, DISPATCH_PROPERTYGET, VT_DISPATCH, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetStayInSync(BOOL bNewValue)
{

	static BYTE parms[] =
		VTS_BOOL;
	InvokeHelper(0x427, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 bNewValue);
}

BOOL C_Recordset::GetStayInSync()
{

	BOOL result;
	InvokeHelper(0x427, DISPATCH_PROPERTYGET, VT_BOOL, (void*)&result, NULL);
	return result;
}

CString C_Recordset::GetString(long StringFormat, long NumRows, LPCTSTR ColumnDelimeter, LPCTSTR RowDelimeter, LPCTSTR NullExpr)
{

	CString result;
	static BYTE parms[] =
		VTS_I4 VTS_I4 VTS_BSTR VTS_BSTR VTS_BSTR;
	InvokeHelper(0x426, DISPATCH_METHOD, VT_BSTR, (void*)&result, parms,
		StringFormat, NumRows, ColumnDelimeter, RowDelimeter, NullExpr);
	return result;
}

CString C_Recordset::GetDataMember()
{

	CString result;
	InvokeHelper(0x428, DISPATCH_PROPERTYGET, VT_BSTR, (void*)&result, NULL);
	return result;
}

void C_Recordset::SetDataMember(LPCTSTR lpszNewValue)
{

	static BYTE parms[] =
		VTS_BSTR;
	InvokeHelper(0x428, DISPATCH_PROPERTYPUT, VT_EMPTY, NULL, parms,
		 lpszNewValue);
}

long C_Recordset::CompareBookmarks(const VARIANT& Bookmark1, const VARIANT& Bookmark2)
{

	long result;
	static BYTE parms[] =
		VTS_VARIANT VTS_VARIANT;
	InvokeHelper(0x429, DISPATCH_METHOD, VT_I4, (void*)&result, parms,
		&Bookmark1, &Bookmark2);
	return result;
}

C_Recordset C_Recordset::Clone(long LockType)
{

	LPDISPATCH pDispatch;
	static BYTE parms[] =
		VTS_I4;
	InvokeHelper(0x40a, DISPATCH_METHOD, VT_DISPATCH, (void*)&pDispatch, parms,
		LockType);
	return C_Recordset(pDispatch);
}



void C_Recordset::Resync(long AffectRecords, long ResyncValues)
{

	static BYTE parms[] =
		VTS_I4 VTS_I4;
	InvokeHelper(0x400, DISPATCH_METHOD, VT_EMPTY, NULL, parms,
		 AffectRecords, ResyncValues);
}



#include "stdafx.h"
#include "ADOConn.h"

#ifdef _DEBUG
#undef THIS_FILE
static char THIS_FILE[]=__FILE__;
#define new DEBUG_NEW
#endif


ADOConn::ADOConn()
{

}

ADOConn::~ADOConn()
{

}

void  ADOConn::OnInitADOConn()
{
	 
	::CoInitialize(NULL);
  
	try
	{
		
		m_pConnection.CreateInstance("ADODB.Connection");
		
		_bstr_t strConnect = "Provider=SQLNCLI.1;Password=sa;Persist Security Info=True;User ID=sa;Initial Catalog=Stock;Data Source=localhost ";
		m_pConnection->Open(strConnect,"","",adModeUnknown);
	}

	catch(_com_error e)
	{
	
		AfxMessageBox(e.Description());
	}
}


_RecordsetPtr&  ADOConn::GetRecordSet(_bstr_t bstrSQL)
{
	try
	{
	
		if(m_pConnection==NULL)
			OnInitADOConn();
		
		m_pRecordset.CreateInstance(__uuidof(Recordset));
	
		m_pRecordset->Open(bstrSQL,m_pConnection.GetInterfacePtr(),adOpenDynamic,adLockOptimistic,adCmdText);
	}
	
	catch(_com_error e)
	{
		
		AfxMessageBox(e.Description());
	}

	return m_pRecordset;
}


BOOL ADOConn::ExecuteSQL(_bstr_t bstrSQL)
{

	try
	{
	
		if(m_pConnection == NULL)
			OnInitADOConn();
	
		m_pConnection->Execute(bstrSQL,NULL,adCmdText);
		return true;
	}
	catch(_com_error e)
	{

		AfxMessageBox(e.Description());
		return false;
	}
}

void ADOConn::ExitConnect()
{

	if (m_pRecordset != NULL)
		m_pRecordset->Close();
	m_pConnection->Close();

	::CoUninitialize();
}

