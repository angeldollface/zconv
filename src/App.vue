<!--
ZCONV by Alexander Abraham, a.k.a. "Angel Dollface".
Licensed under the MIT license.
-->

<!--
Using our component as a virtual DOM element
and adding some flowery stuff.
-->
<template>
 <!--Main heading.-->
 <h1>ZCONV</h1>

 <!--Main div holding the main component.-->
 <div class="content">
  <NumConverter/>
 </div>

</template>

<!--
Importing our component with Vue's help.
-->
<script>
// Importing the main component.
import NumConverter from './components/NumConverter.vue';

// Registering the main component.
export default {
  name: 'App',
  components: {
    NumConverter
  }
}
</script>

<!--
Styling our component.
-->
<style lang="scss">
// Setting up the app's style constants.
$stdPadding: 20px;
$stdFont: 'MC';
$bgColor: #FFACA5;
$stdBorderRadius: 25px;
$divGradientOne: #EA1573;
$divGradientTwo: #FF7BAC;
$contentColor: #FFFFFF;
$stdBorderRadius: 25px;

// Importing the app's desktop
// and responsive layouts, respectively.
@import './sass/desktop.scss';
@import './sass/responsive.scss';

</style>
