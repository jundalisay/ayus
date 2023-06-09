<!-- Messenger Chat Plugin Code -->
    <div id="fb-root"></div>

    <!-- Your Chat Plugin code -->
    <div id="fb-customer-chat" class="fb-customerchat">
    </div>

    <script>
      var chatbox = document.getElementById('fb-customer-chat');
      chatbox.setAttribute("page_id", "107480018751881");
      chatbox.setAttribute("attribution", "biz_inbox");
    </script>

    <!-- Your SDK code -->
    <script>
      window.fbAsyncInit = function() {
        FB.init({
          xfbml            : true,
          version          : 'v17.0'
        });
      };

      (function(d, s, id) {
        var js, fjs = d.getElementsByTagName(s)[0];
        if (d.getElementById(id)) return;
        js = d.createElement(s); js.id = id;
        js.src = 'https://connect.facebook.net/en_US/sdk/xfbml.customerchat.js';
        fjs.parentNode.insertBefore(js, fjs);
      }(document, 'script', 'facebook-jssdk'));
    </script>



<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-46YXT3HWMK"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-46YXT3HWMK');
</script>


        {{ with .Params.Video }}
          <div class="img-border rounded mb-5 mb-md-0">
            <img src="{{ .videoThumb | absURL }}" alt="video thumb" class="img-fluid rounded">
            <a data-toggle="modal" data-src="{{ .videoURL | safeURL }}" data-target="#videoModal2"
              class="text-color video-modal content-center"><i class="ti-control-play bg-gradient btn-play-lg"></i></a>
            <!-- Modal -->
            <div class="modal fade" id="videoModal2" tabindex="-1" role="dialog" aria-hidden="true">
              <div class="modal-dialog modal-dialog-centered" role="document">
                <div class="modal-content border-0 rounded-0">
                  <iframe width="560" height="315" src="" id="video2" frameborder="0"
                    allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
                    allowfullscreen></iframe>
                </div>
              </div>
            </div>
          </div>
        {{ end }}


    <form action="{{ .Site.Params.contact.formAction }}" method="POST">
<!--       <input type="text" class="form-control mb-2" id="name" name="email[name]" placeholder="Your Name">
      <input type="email" class="form-control mb-2" id="email" name="email[email]" placeholder="Your Email">
      <textarea name="email[content]" id="message" class="form-control mb-2" placeholder="Your Message"></textarea>
      <input name="email[address]" id="source" type="hidden" value="{{ .Permalink }}">             -->
      <input type="text" class="form-control mb-2" id="name" name="name" placeholder="Your Name">
      <input type="email" class="form-control mb-2" id="email" name="email" placeholder="Your Email">
      <textarea name="message" id="message" class="form-control mb-2" placeholder="Your Message"></textarea>
      <input type="hidden" id="source" name="address" value="{{ .Permalink }}">                  
      <button type="submit" value="send" class="btn btn-block btn-outline-primary rounded">Send Now</button>
    </form>
