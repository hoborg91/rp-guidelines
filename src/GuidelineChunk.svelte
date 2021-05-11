<script>
    export let guideline;
</script>

<div>
    {guideline.message}
    {#if guideline.imgLink}
    <div class="img-common">
        <a href="{guideline.imgLink}"><img src="{guideline.imgLink}" alt="{guideline.imgDescription}" title={guideline.imgDescription} width=200/></a>
    </div>
    {/if}
</div>
{#if guideline.bestPractices}
{#each guideline.bestPractices as bestPractices}
<div class="best-practices-div">
    <table>
        <tbody>
            <tr>
                <td class="best-practices-td"><div title="Пример для подражания" class="best-practices-sign">&#128081;</div></td>
                <td>
                    {#if bestPractices.imgLink}
                    <div>
                        <a href="{bestPractices.imgLink}"><img src="{bestPractices.imgLink}" alt="{bestPractices.imgDescription}" title={bestPractices.imgDescription} width=200/></a>
                    </div>
                    {/if}
                    <div class="best-practices-message">{bestPractices.message}</div>
                    <small class="best-practices-reference"><a href="{bestPractices?.linkHref}">{bestPractices.linkCaption} | {bestPractices?.linkHref}</a></small>
                </td>
            </tr>
        </tbody>
    </table>
</div>
{/each}
{/if}

<style>
    .best-practices-div {
        background-color: azure;
        /*border: 1px solid lightblue;*/
        font-size: small;
        margin: 5px;
        padding-top: 5px;
        padding-bottom: 5px;
    }

    .best-practices-td
    {
        vertical-align: top;
        cursor: default;
    }

    .img-common {
        margin-top: 5px;
        margin-bottom: 5px;
    }
</style>