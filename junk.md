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
