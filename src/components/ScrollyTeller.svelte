<script>
  import Scroller from "@sveltejs/svelte-scroller";
  import Topic from "./Topic.svelte";
  import P2 from "./P2.svelte";
  import P3 from "./P3.svelte";
  import P4 from "./P4.svelte";
  import P5 from "./P5.svelte";
  import P6 from "./P6.svelte";
  import P8 from "./P8.svelte";
  import P9 from "./P9.svelte";
  import P10 from "./P10.svelte";
  import P11 from "./P11.svelte";
  import P12 from "./P12.svelte";
  import P13 from "./P13.svelte";
  import P14 from "./P14.svelte";
  import P15 from "./P15.svelte";
  import P16 from "./P16.svelte";
  import P17 from "./P17.svelte";
  import P18 from "./P18.svelte";
  import P19 from "./P19.svelte";
  import P20 from "./P20.svelte";
  import P21 from "./P21.svelte";
  import Map from "./Mapping.svelte";

  import InteractiveSection from "./InteractiveSection.svelte";

  import { geoMercator } from "d3-geo";

  let count, index, offset, progress;

  let width, height;

  let geoJsonToFit = {
    type: "FeatureCollection",
    features: [
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [1, 0],
        },
      },
      {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: [0, 1],
        },
      },
    ],
  };


  
</script>

<Scroller
  top={0.0}
  bottom={1}
  threshold={0.5}
  bind:count
  bind:index
  bind:offset
  bind:progress
>
  <div
    class="background"
    slot="background"
    bind:clientWidth={width}
    bind:clientHeight={height}
  >
    
    <Map {index} />
    
    <div class="progress-bars">
      <p>current section: <strong>{index + 1}/{count}</strong></p>
      <progress value={count ? (index + 1) / count : 0} />

      <p>offset in current section</p>
      <progress value={offset || 0} />

      <p>total progress</p>
      <progress value={progress || 0} />
    </div>


    

  </div>

  <div class="foreground" slot="foreground">
    
    <section>
      <div> 
        <div><Topic/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P2 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P3 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P4 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P5 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P6 {index}/></div>
      </div>
    </section>
    
    <section> </section>

    <section>
      <div> 
        <div><P8 {index}/></div>
      </div>
    </section>
    
    <section>
      <div> 
        <div><P9 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P10 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P11 {index}/></div>
      </div>
    </section>
    
    <section>
      <div> 
        <div><P12 {index}/></div>
      </div>
    </section>
    
    <section>
      <div> 
        <div><P13 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P14 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P15 {index}/></div>
      </div>
    </section>
    
    <section>
      <div> 
        <div><P16 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P17 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P18 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P19 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P20 {index}/></div>
      </div>
    </section>

    <section>
      <div> 
        <div><P21 {index}/></div>
      </div>
    </section>

    
  </div>
</Scroller>

<style>
  .background {
    width: 100%;
    height: 100vh;
    position: relative;
    outline: green solid 3px;
  }

  .foreground {
    width: 100%;
    margin: 0 auto;
    height: auto;
    position: relative;
    outline: red solid 3px;
  }

  .progress-bars {
    position: absolute;
    background: rgba(170, 51, 120, 0.2) /*  40% opaque */;
    visibility: visible;
  }

  section {
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.2); /* 20% opaque */
    /* color: white; */
    text-align: center;
    color: black;
    margin: 0 0 0 0;
  }

:global(body) {
  margin: 0;
}

</style>
