# 建置Hls中轉Rtmp的服務

此服務僅作為中繼代轉之用，僅有一個Http Port做為API接口接收Json內容用

## 內容

 - HlsToRtmp.exe：windows版本執行檔
 - 需另行下載ffmpeg.exe置於同一目錄下
 　(下載地址　https://github.com/BtbN/FFmpeg-Builds/releases)


## 運行方式
以command line執行HlsToRtmp即可

 - 執行
       HlsToRtmp (預設8000port做http監聽，需改Port可由下一項運行)
       
 - 修改監聽並執行(可修改別的Port例8001，不改Port就用上方執行即可)
       HlsToRtmp -p 8001 (改為8001監聽)

## API接收內容

>JSON接收內容
> [
>　 {
>　　"key":"識別Key (影片id)", 
>　　"src":"來源(HLS)",
>　　"dst":"目的(RTMP)"
>　}
> ]

