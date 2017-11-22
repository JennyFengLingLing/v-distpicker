<template>
  <div class="block">
    <h4 class="text-center">Base Usage</h4>
    <basic></basic>
    <sort></sort>
    <quick-pass-city></quick-pass-city>
    <placeholders></placeholders>
    <default-value></default-value>
    <hide-area></hide-area>
    <only-province></only-province>
    <trigger-event></trigger-event>
    <reset-button></reset-button>
  </div>
</template>

<script>
import Basic from './Basic'
import Sort from './Sort'
import QuickPassCity from './QuickPassCity'
import Placeholders from './Placeholders'
import DefaultValue from './DefaultValue'
import HideArea from './HideArea'
import OnlyProvince from './OnlyProvince'
import TriggerEvent from './TriggerEvent'
import ResetButton from './ResetButton'

export default {
  components: {
    Basic,
    Sort,
    QuickPassCity,
    Placeholders,
    DefaultValue,
    HideArea,
    OnlyProvince,
    TriggerEvent,
    ResetButton,
  },
}
</script>
