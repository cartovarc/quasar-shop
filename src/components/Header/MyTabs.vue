<template>
  <div class="text-subtitle1 text-weight-medium absolute-center">
    <ul>
      <li><a href="#">Makeup</a></li>
      <li><a href="#">Hair</a></li>
      <li><a href="#">Skincare</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>

<style lang="scss">
$red: black;
$brown: black;
$whitey: #f0f0f0;

$duration: 0.2s;
$distance: 8px;
$easeOutBack: cubic-bezier(0.175, 0.885, 0.32, 1.275);

ul {
  list-style-type: none;
  margin: 0;
  text-align: center;

  li {
    display: inline-block;
    margin: 0 20px;
  }
}
a {
  color: $brown;
  position: relative;
  text-transform: uppercase;
  text-decoration: none;
  padding-bottom: 8px;

  &:before,
  &:after {
    content: "";
    position: absolute;
    bottom: 2px;
    left: 0;
    right: 0;
    height: 2px;
    background-color: $red;
  }
  &:before {
    opacity: 0;
    transform: translateY(-$distance);
    transition: transform 0s $easeOutBack, opacity 0s;
  }
  &:after {
    opacity: 0;
    transform: translateY($distance/2);
    transition: transform $duration $easeOutBack, opacity $duration;
  }
  &:hover,
  &:focus {
    &:before,
    &:after {
      opacity: 1;
      transform: translateY(0);
    }
    &:before {
      transition: transform $duration $easeOutBack, opacity $duration;
    }
    &:after {
      transition: transform 0s $duration $easeOutBack, opacity 0s $duration;
    }
  }
}
</style>
