<script>
  import CenteredScroller from './sections/CenteredScroller.svelte';
  import LeftAlignedExample from "./sections/LeftAlignedExample.svelte";
  import RightAlignedExample from "./sections/RightAlignedExample.svelte";
  import ImageExample from "./sections/ImageExample.svelte";
  import TitleSection from "./sections/TitleSection.svelte";
  import InteresectionObserverBasicExample from "./sections/InteresectionObserverBasicExample.svelte";
  import IntersectionObserverAlertExample from "./sections/IntersectionObserverAlertExample.svelte";
  import DisappearingDuckExample from "./sections/DisappearingDuckExample.svelte";
  import IntersectionObserverSectionCard from "./sections/IntersectionObserverSectionCard.svelte";
  import IntersectionObserverListExample from "./sections/IntersectionObserverListExample.svelte";
  import Typewritter from './sections/Typewritter.svelte';
  import ObservedTypeCard from './sections/ObservedTypeCard.svelte';
  import BWDCTableau from './lib/BWDCTableau.svelte';
  import ProjectAmount from './sections/ProjectAmount.svelte';
  import EndSection from './sections/EndSection.svelte';
</script>

<main>
  <TitleSection />
  <CenteredScroller />
  <IntersectionObserverListExample />
  <Typewritter />
  <BWDCTableau />
  <ProjectAmount />
  <ImageExample />
  <EndSection />
  <RightAlignedExample />
  <LeftAlignedExample />
  <IntersectionObserverSectionCard />
  <InteresectionObserverBasicExample />
  <IntersectionObserverAlertExample />
  <DisappearingDuckExample />
</main>
