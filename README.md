# UploadMagnetSDK
.NET API Library for uploadmagnet.com
> [Supported File Sharing Services](https://github.com/loudKode/UploadMagnetSDK/wiki/Supported-File-Sharing-Services)
# Functions:
```vb.net
    Function UserInfo() As Task(Of JSON_UserInfo)
    Function SetFileShareLogins(FileShareService As UPMutilities.FileShareServiceEnum, Email As String, Password As String, Upload As Boolean, Download As Boolean, SetDefault As Boolean) As Task(Of Boolean)
    Function RemoteUpload(UrlToUpload As String, UploadTo As UPMutilities.FileShareServiceEnum) As Task(Of JSON_RemoteUpload)
    Function RemoteUploadStatus(JobID As String) As Task(Of JSON_RemoteUploadStatus)
    Function DirectLink(XfileMirrorUrl As String) As Task(Of String)
    Function GetFileID(XfileMirrorUrl As String) As Task(Of JSON_FileID)
    Function FileMetadata(FileID As String) As Task(Of JSON_FileMetadata)
    Function CheckFile(JobID As String) As Task(Of String)
    Function APIRemoteUpload(ApiKey As String, UrlToUpload As String, FileShareTag As UPMutilities.FileShareTagEnum) As Task(Of String)
```

# Example:
```vb.net
Dim logn = Await UploadMagnetSDK.GetToken.GetToken("user@g.com", "pass123")
Dim Clnt As UploadMagnetSDK.IClient = New UploadMagnetSDK.XClient(logn)
Dim RSLT = Await Clnt.UserInfo()
Dim RSLT = Await Clnt.SetFileShareLogins(UploadMagnetSDK.UPMutilities.FileShareServiceEnum.solidfiles, "user", "pass", True, False, True)
Dim RSLT = Await Clnt.RemoteUpload("https://img.1fichier.com/logo.png", UploadMagnetSDK.UPMutilities.FileShareServiceEnum.solidfiles)
Dim RSLT = Await Clnt.DirectLink("http://www.uploadmagnet.com/se_879hdyp1iupz")
Dim RSLT = Await Clnt.RemoteUploadStatus("1562147337152")
Dim RSLT = Await Clnt.GetFileID("http://www.uploadmagnet.com/879hdyp1iupz/logo.png")
Dim RSLT = Await Clnt.FileMetadata("227689")
Dim RSLT = Await Clnt.CheckFile("1562147337152")
```
