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
        <textarea class="freeform" />
        <div class="emoji-select">
            <div class="emoji" />
            <div class="emoji" />
            <div class="emoji" />
            <div class="emoji" />
        </div>
        <div class="emoji-select">
            <div class="emoji" />
            <div class="emoji" />
            <div class="emoji" />
            <div class="emoji -gray" />
        </div>
        <div class="emoji-select">
            <div class="emoji -spacer" />
            <div class="emoji -spacer" />
            <div class="emoji -spacer" />
            <div class="emoji -dark" />
        </div>
    </div>

    <div class="submit">
        <input type="button" value="Submit" />
    </div>
</div>

<style lang="scss">
    .container {
        margin: 1.5em;

        display: flex;
        flex-direction: column;
        justify-content: space-between;
        height: 100%;
    }

    .time-header {
        > .prefix {
            font-size: 2em;
        }

        > .indicator {
            font-size: 2.5em;
        }
    }

    .mood-input {
        > .freeform {
            border-radius: 1em;
            width: 100%;
            height: 5em;

            background-color: #eff2f7;
            margin: 3em 0 1em;
        }

        > .emoji-select {
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
            width: 100%;
            justify-content: space-around;
            margin: 1em 0;

            > .emoji {
                width: 2.5em;
                height: 2.5em;
                background-color: #ffd55f;
                border-radius: 2.5em;

                &.-spacer {
                    pointer-events: none;
                    visibility: hidden;
                }

                &.-gray {
                    background-color: #eff2f7;
                }

                &.-dark {
                    background-color: #3c4858;
                }
            }
        }
    }

    .submit {
    }
</style>
