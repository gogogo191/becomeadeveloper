GG3 sqlite 사용 방법입니다.

현재 제공되는 GG3 개발자 펌웨어가 root가 열려 있어 콘솔 연결 없이 사용 가능합니다.

 

 

1.     sqlite3-3.22.0 버전 다운로드

https://github.com/EXALAB/sqlite3-android/raw/master/binary/armeabi-v7a/sqlite3

 

2.     다운받은 파일 GG3 /sdcard 로 업로드

> adb push sqlite3 sdcard/

3.     GG3는 /sdcard 실행 권한 불가 /data로 파일 이동 필요

$ su

#mv /sdcard/sqlite3 /data/    

4.     실행 퍼미션 추가

# chmod +x /data/sqlite3   

5.     런처 DB 실행 (네이티브앱 각자 DB파일 위치 확인후 실행)

# /data/sqlite3 /data/data/com.kt.gigagenie.launcher/databases/launcherCommon.db
