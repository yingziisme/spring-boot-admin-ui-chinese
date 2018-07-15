<!--
  - Copyright 2014-2018 the original author or authors.
  -
  - Licensed under the Apache License, Version 2.0 (the "License");
  - you may not use this file except in compliance with the License.
  - You may obtain a copy of the License at
  -
  -     http://www.apache.org/licenses/LICENSE-2.0
  -
  - Unless required by applicable law or agreed to in writing, software
  - distributed under the License is distributed on an "AS IS" BASIS,
  - WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  - See the License for the specific language governing permissions and
  - limitations under the License.
  -->

<template>
  <section class="section heapdump">
    <div>
      <div class="message is-warning">
        <div class="message-body">
          内存快照可能包含 <strong>敏感信息</strong>.<br>请谨慎处理.
          <br>A heap dump may contain <strong>sensitive data</strong>.<br>Please handle with care.
        </div>
      </div>
      <div class="message is-warning">
        <div class="message-body">
          获取一次内存快照可能会消耗较大的cup和内存
          <br>Dumping the heap may be expensive in terms of cpu and disk space.
        </div>
      </div>
      <a class="button is-primary" :href="`instances/${instance.id}/actuator/heapdump`" target="_blank">
        <font-awesome-icon icon="download"/>&nbsp;下载(Download Heap Dump)
      </a>
    </div>
  </section>
</template>

<script>
  import Instance from '@/services/instance';

  export default {
    props: {
      instance: {
        type: Instance,
        required: true
      }
    }
  }
</script>

<style lang="scss">
  .heapdump {
    display: flex;
    justify-content: space-around;

    & > div {
      display: flex;
      flex-direction: column;
    }
  }
</style>
