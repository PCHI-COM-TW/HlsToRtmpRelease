# 建置Hls中轉Rtmp的服務

此服務僅作為中繼代轉之用，僅有一個Http Port做為API接口接收Json內容用

## 內容

 - HlsToRtmp.exe：windows版本執行檔
 - 需另行下載ffmpeg.exe置於同一目錄下
 　(下載地址　https://github.com/BtbN/FFmpeg-Builds/releases)
 - register.bat 註冊HlsToRtmp服務
 - start.bat 啟動HlsToRtmp服務
 - stop.bat 停止HlsToRtmp服務
 - delete.bat 刪除HlsToRtmp服務(停用時需等幾秒才生效)
 - status.bat 查HlsToRtmp服務運行狀態


## 運行方式一
以command line執行HlsToRtmp即可

 - 執行
       HlsToRtmp (預設8000port做http監聽，需改Port可由下一項運行)
       
 - 修改監聽並執行(可修改別的Port例8001，不改Port就用上方執行即可)
       HlsToRtmp -p 8001 (改為8001監聽)

## 運行方式二 (即註冊進windows名為HlsToRtmp的服務)
   1.執行register.bat (若修改port要改binpath=的內容加 -p 8001，即對應Port 8001)
   2.執行start.bat


## API接收內容

>JSON接收內容
```json
[
 {
  "key":"識別Key (影片id)",
  "src":"來源(HLS)",
  "dst":"目的(RTMP)"
 }
]
```