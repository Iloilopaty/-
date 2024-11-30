<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>サンタ殿へ</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bulma@0.9.3/css/bulma.min.css">
  </head>
  <body>
    <div id="notification" class="notification" style="position: fixed; z-index: 1; width: 100%;">
      <button id="delete" class="delete"></button>
      ※サンタ殿へ
    </div>
    <section class="hero is-warning">
      <div class="hero-body">
        <div class="container">
          <div class="notification is-primary">
            <p>写真を撮影しました</p>
          </div>
          <h1 class="title is-size-1">サンタ殿へ</h1>
          <p class="is-size-4">お前には5つの願いを叶えてもらう</p>
           <p class="is-size-4">カウンターが0になるまでに願いが叶えられなれなかったとき…</p>
          <p>写真をXに公開されるだろう</p>
          <p>5つの願いは下にある</p>
          <p class="is-size-4 has-text-danger"><span class="is-size-3 has-text-weight-bold"></span>すぐに叶えろ</p>
          <div class="notification is-danger">
            <p class="is-size-3 has-text-centered">
              残り
              <span id="hour">6</span>時間
              <span id="min">0</span>分
              <span id="sec">0</span>秒
            </p>
            <progress class="progress" max="100"></progress>
          </div>
          <p>1つ</p>
          <p>この商品を買いたまえ</p>
          <p>＜リンク</p>
          <p></p>
          <p class="has-text-danger">https://www.amazon.co.jp/FURLOU-%E9%BB%92%E3%81%AEUSB%E3%82%AD%E3%83%BC%E3%83%9C%E3%83%BC%E3%83%89%E3%81%8A%E3%82%88%E3%81%B3%E3%83%9E%E3%82%A6%E3%82%B9%E3%82%B3%E3%83%B3%E3%83%90%E3%83%BC%E3%82%BF%E3%83%BCNSwitch-360Professional%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B5%E3%83%AA/dp/B0CMZXFTWV
             <p>2つ</p>
          <p>この商品も買いたまえ</p>
          <p>＜リンク＞</p>
          <p></p>
        </div>
      </div>
    </section>
    <section class="section">
      <div class="container">
        <h2 class="title">サンタ情報</h2>
        <table class="table is-striped is-fullwidth">
          <tr>
            <td>読み込み端末情報</td>
            <td id="device"></td>
          </tr>
          <tr>
            <td>読み込み日時</td>
            <td id="date"></td>
          </tr>
        </table>
     <td></td>
          </tr>
        </table>
      </div>
    </section>
    <script src="https://code.jquery.com/jquery-3.6.0.slim.min.js" integrity="sha256-u7e5khyithlIdTpu22PHhENmPcRdFiHRjhAuHcs05RI=" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/platform/1.3.6/platform.min.js"></script>
    <script type="text/javascript">
      // history.pushState(null, null, location.href);
      // $(window).on('popstate', function(){
      //   history.go(1);
      // });
      const se = new Audio(
        "https://dl.dropbox.com/s/pjf5iswhy43fc1f/camera-shutter3.mp3"
      );
      se.play();
      let c = 6 * 60 * 60;
      setInterval(() => {
        $("#hour").text(Math.floor(c / 3600));
        $("#min").text(Math.floor((c % 3600) / 60));
        $("#sec").text(Math.floor(c % 60));
        c = c - 1;
      }, 1000);
      $("#device").text(platform.description);
      $("#date").text(new Date().toLocaleString("ja-JP"));
      $("#delete").click(() => {
        $("#notification").addClass("is-hidden")
      });
    </script>
  </body>
</html>
