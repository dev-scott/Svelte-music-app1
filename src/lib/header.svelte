<script>
  // let src1 = '/public/build/1.jpg';
  // let src2 = '/public/build/play.png';
  // let src3 = '/public/build/music.png';
  // let src4 = '/public/build/more.png';
  // let src5 = '/public/build/personnage.png';
  //     import Fa from 'svelte-fa/src/fa.svelte'
  // import { faCaretDown, faCaretUp } from '@fortawesome/free-solid-svg-icons/index.es'
 
  import Fa from 'svelte-fa';
  import { faMusic } from '@fortawesome/free-solid-svg-icons';
  import { faPlay } from '@fortawesome/free-solid-svg-icons';
  import { faHouse } from '@fortawesome/free-solid-svg-icons';
  import { faMagnifyingGlass } from '@fortawesome/free-solid-svg-icons';
  import { faBridgeLock } from '@fortawesome/free-solid-svg-icons';
  import { faPlusSquare } from '@fortawesome/free-solid-svg-icons';
  import { faHeart } from '@fortawesome/free-solid-svg-icons';
  import { faArrowRightLong } from '@fortawesome/free-solid-svg-icons';
  import { faArrowLeftLong } from '@fortawesome/free-solid-svg-icons';
  import { faVolumeDown } from '@fortawesome/free-solid-svg-icons';
  // import { faArrowLeftLong } from '@fortawesome/free-solid-svg-icons';



import {artists} from '../Data/data';
  import {songCategorie} from '../Data/data'

  import {songs} from '../Data/data'


</script>

<header>
  <div class="menu_side">
    <h1><img src={src4} alt="" /></h1>
    <div class="playlist">
      <h4 class="active">
        <Fa class="faIcon" color="white" icon={faHouse} />
        <h3>Playlist</h3>
      </h4>
      <h4>
        <Fa color="white" icon={faMagnifyingGlass} />
        <h3>Dernier suivi</h3>
      </h4>
      <h4>
        <Fa color="white" icon={faBridgeLock} />
        <h3>Recommande</h3>
      </h4>
    </div>
    <div class="ListPlaylist playlist">
      <h4>
        <Fa color="white" icon={faPlusSquare} />
        <h3>Creer une playlist</h3>
      </h4>
      <h4>
        <Fa color="white" icon={faHeart} />
        <h3>Titre like</h3>
      </h4>
    </div>




    <div class="menu_song">

      {#each songs as single (single.id)}
        


      <li class="songItem">
        <span>{single.numero}</span>
        <img src={single.img} alt="" />
        <h5>


          {single.title}

          <div class="subtitle">{single.subtitle}</div>

          <img src={single.img} id="2" class="faPlay" alt="" />
        </h5>
      </li>

            {/each}


    </div>






    
  </div>
  <div class="song_side">
    <nav>
      <ul>
        <li>Discover <span /></li>
        <li>My Library</li>
        <li>Radio</li>
      </ul>
      <div class="search">
        <span class="bi"> <Fa color="white" icon={faMagnifyingGlass} /></span>
        <input type="text" placeholder="Search Music ..." />
      </div>

      <div class="user">
        <img src="" alt="" />
      </div>
    </nav>

    <div class="content">
      <h1>Sado Ryan-Scott</h1>

      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Assumenda totam
        dignissimos vitae nihil quas distinctio. <br />
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Minima?
      </p>

      <div class="buttons">
        <button>Play</button>
        <button>Follow</button>
      </div>
    </div>





    {#each songCategorie as song  (song.id)}
      
    <div class="popular_song">





      <div class="h4">
        <h4>{song.title}</h4>

        <div class="btn_s">
          <span id="left_scroll">
            <Fa color="white" icon={faArrowLeftLong} />
          </span>
          <span id="right_scroll">
            <Fa color="white" icon={faArrowRightLong} />
          </span>
        </div>
      </div>



      <div class="pop_song">


        {#each artists  as artist (artist.id) }
          

        <li class="songItem">
          <div class="img_play">
            <img src={artist.img} alt="Sado scott" />

            <span class=" bi playListPlay" id="7">
              <Fa class="faIcon" color="white" icon={faPlay} />
            </span>
          </div>

          <h5>
            {artist.title} <br />
            <div class="subtitle">{artist.subtitle}</div>
            <!-- <img src={src2} id="10" class="faPlay" alt="" /> -->
          </h5>
        </li>

      {/each}

     
      </div>




    </div>

        {/each}


    <!-- <div class="popular_song">
      <div class="h4">
        <h4>Artiste prefere</h4>

        <div class="btn_s">
          <span id="left_scrolls">
            <Fa color="white" icon={faArrowLeftLong} />
          </span>
          <span id="right_scrolls">
            <Fa color="white" icon={faArrowRightLong} />
          </span>
        </div>
      </div>




      <div class=" popular_artist">
        <li class="songItem">
          <div class="img_play">
            <img src={src1} alt="Sado scott" />

            <span class=" bi playListPlay" id="7">
              <Fa class="faIcon" color="white" icon={faPlay} />
            </span>
          </div>

          <h5>
            On My Way <br />
            <div class="subtitle">Alain Walker</div>
          </h5>
        </li>
      </div>





    </div> -->




  </div>

  <div class="master_played">
    <div class="wave">
      <div class="wave1" />
      <div class="wave1" />
      <div class="wave1" />
    </div>
    <img src={src1} alt="" />
    <h5>
      On My Way <br />
      <div class="subtitle">Alain Walker</div>
    </h5>
    <!-- <img src={src2} id="11" class="faPlay" alt=""> -->

    <div class="icon">
      <span class="iconique"> <Fa color="white" icon={faArrowLeftLong} /></span>
      <span class="iconique"> <Fa color="white" icon={faPlay} /> </span>
      <span class="iconique">
        <Fa color="white" icon={faArrowRightLong} />
      </span>
    </div>
    <span id="currentStart">00:00</span>
    <div class="barre">
      <input type="range" id="seek" min="0" value="0" max="100" />
      <div class="barre2" id="barre2" />
      <div class="dot" />
    </div>
    <span id="currentEnd">00:00</span>

    <div class="vol">
      <span class="bi">
        <Fa color="white" icon={faVolumeDown} />
      </span>
      <input type="range" id="vol" min="30" value="0" max="100" />
      <div class="vol_barre" />
      <div class="dot" id="vol_dot" />
    </div>
  </div>
</header>

<style lang="scss">
  @import '../Style/header.scss';
</style>
