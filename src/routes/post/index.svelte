<script lang="ts">
    import { time } from './stores';

    const formatter = new Intl.DateTimeFormat('en', {
        dateStyle: 'full',
        timeStyle: 'medium',
    });
</script>

<div class="container">
    <div class="time-header">
        <div class="prefix">Today is</div>
        <div class="indicator">{formatter.format($time)}</div>
    </div>

    <div class="mood-input">
        <input class="freeform" type="text" />
        <div class="emoji-select">
            <div class="emoji">_</div>
            <div class="emoji">_</div>
            <div class="emoji">_</div>
            <div class="emoji">_</div>
            <div class="emoji">_</div>
            <div class="emoji">_</div>
            <div class="emoji">_</div>
        </div>
        <div class="image">_</div>
    </div>

    <div class="submit">
        <input type="button" value="Submit" />
    </div>
</div>

<style lang="scss">
    .container {
        margin: 20px;
    }

    .time-header {
        > .prefix {
            font-size: 24px;
        }

        > .indicator {
            font-size: 40px;
        }
    }
</style>
