# Laravel 10 錯誤捕獲器

引入 nunomaduro 的 larastan 套件來擴增使用 PHPStan 通過靜態分析儘早捕獲錯誤，預設情況下，它將使用級別 0 來檢查「明顯」的錯誤，例如傳遞額外的引數或語法錯誤。隨著時間的推移，可以提高階別以進行更嚴格的分析。

## 使用方式
- 把整個專案複製一份到你的電腦裡，這裡指的「內容」不是只有檔案，而是指所有整個專案的歷史紀錄、分支、標籤等內容都會複製一份下來。
```sh
$ git clone
```
- 將 __.env.example__ 檔案重新命名成 __.env__，如果應用程式金鑰沒有被設定的話，你的使用者 sessions 和其他加密的資料都是不安全的！
- 當你的專案中已經有 composer.lock，可以直接執行指令以讓 Composer 安裝 composer.lock 中指定的套件及版本。
```sh
$ composer install
```
- 產生 Laravel 要使用的一組 32 字元長度的隨機字串 APP_KEY 並存在 .env 內。
```sh
$ php artisan key:generate
```
- 執行二進位制檔案用於分析目錄並輸出遇到的任何錯誤。
```sh
$ ./vendor/bin/phpstan analyse {掃描路徑} {-c 設定檔}
```

----

## 畫面截圖
![](https://i.imgur.com/edpdAh2.png)
> 執行二進位制檔案檢查
