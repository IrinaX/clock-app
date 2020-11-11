<template>
  <div class="number">
    <div class="line a"></div>
    <div class="group-line fb">
      <div class="line f"></div>
      <div class="line b"></div>
    </div>
    <div class="line g"></div>
    <div class="group-line ec">
      <div class="line e"></div>
      <div class="line c"></div>
    </div>
    <div class="line d"></div>
  </div>
</template>

<style lang="scss" scoped>
$primary: #3C76CD;
$shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
$radius: 5px;
@keyframes appear {
  0% {
    opacity: 0;
  }
}

.number {
  margin-right: 10px;

  &:nth-child(2n) {
    margin-right: 26px;
    position: relative;

    &:before, &:after {
      content: '';
      position: absolute;
      right: -15px;
      width: 4px;
      height: 4px;
      background: $primary;
    }

    &:before {
      top: 15px;
    }

    &:after {
      bottom: 15px;
    }
  }

  &:last-child {
    margin-right: 0;

    &:before, &:after {
      content: none;
    }
  }

  animation: 1s appear;
  width: 33px;
  height: 61px;

  &_1 {
    .a, .f, .g, .e, .d {
      background: none;
      box-shadow: none;
    }
  }

  &_2 {
    .f, .c {
      background: none;
      box-shadow: none;
    }
  }

  &_3 {
    .f, .e {
      background: none;
      box-shadow: none;
    }
  }

  &_4 {
    .a, .e, .d {
      background: none;
      box-shadow: none;
    }
  }

  &_5 {
    .b, .e {
      background: none;
      box-shadow: none;
    }
  }

  &_6 {
    .b {
      background: none;
      box-shadow: none;
    }
  }

  &_7 {
    .f, .g, .e, .d {
      background: none;
      box-shadow: none;
    }
  }

  &_8 {
    //
  }

  &_9 {
    .e {
      background: none;
      box-shadow: none;
    }
  }

  &_0 {
    .g {
      background: none;
      box-shadow: none;
    }
  }
}

.line {
  background: $primary;
  box-shadow: $shadow;
  border-radius: $radius;
}

.a, .g, .d {
  margin: 0 auto;
  width: 23px;
  height: 5px;
}

.b, .c, .e, .f {
  width: 5px;
  height: 23px;
}

.group-line {
  display: flex;
  justify-content: space-between;
}
</style>
