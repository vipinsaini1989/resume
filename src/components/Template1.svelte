<script>
    export let data;

    const formatDate = (dateStr)=>{
        if (!dateStr) {
            return "Current"
        }
        const options = {  year: 'numeric', month: 'short'};
        return new Date(dateStr).toLocaleDateString({},options);
    }

</script>

<main>
    <div class="container m-sm-3 p-sm-5">
        <div class="row">
            <div class="col-sm-8 print-8">
                <section class="d-sm-flex">
                    <img src={data.personal.photo} class="img-profile d-print-none" alt={data.personal.name}/>
                    <div class="mx-sm-3 mt-4 mt-sm-0">
                        <h1>{data.personal.name}</h1>
                        <p>
                            {data.personal.designation}
                            @ 
                            <a href={data.company.website} class="text-decoration-none" target="_blank">{data.company.name}</a>
                        </p>
                    </div>
                </section>

                <section class="mt-5">
                    <h6 class="text-uppercase text-primary">Work Experience</h6>
                    {#each data.work_experience as project (project.title)}
                    <div class="mt-4">
                        <h5>
                            {project.title}
                            --
                            <span class="fw-light">{project.role}</span>
                        </h5>
                        <div class="fw-bold text-muted">{project.technology}</div>
                        <p>{project.description}</p>
                    </div>
                    {/each}
                </section>

                <section class="mt-5">
                    <h6 class="text-uppercase text-primary">Education</h6>
                    {#each data.education as edu (edu.course)}
                        <div class="mt-4">
                            <h5>
                                {edu.college},<span class="fw-light">{edu.city}</span>
                                --
                                <span class=" fst-italic">{edu.course}</span>
                            </h5>
                            <div class=" text-muted">{formatDate(edu.from)} - {formatDate(edu.to)}</div>
                            <p>{edu.branch}</p>
                        </div>
                    {/each}
                </section>
            </div>
            <div class="col-sm-4 print-4">
                <section>
                    {data.personal.address}
                    <br>
                    {data.personal.city},{data.personal.state}
                    <br>
                    <a href="tel:{data.personal.phone}" class="text-decoration-none">
                        <strong>{data.personal.phone}</strong>
                    </a>
                    <br>
                    <a href="mailto:{data.personal.email}" class="text-decoration-none">
                        <strong>{data.personal.email}</strong>
                    </a>
                </section>

                <section class="mt-4">
                    <h6 class="text-uppercase text-primary">Company</h6>
                    <div class="mt-4">
                        <h5>
                            {data.company.name},<span class="fw-light">{data.company.city}</span>
                            --
                            <span class=" fst-italic">{data.personal.designation}</span>
                        </h5>
                        <div class=" text-muted">{formatDate(data.company.from)} - {formatDate(data.company.to)}</div>
                        <p>{data.company.description}</p>
                        {#if data.company.website}
                            <a href={data.company.website} target="_blank" class="text-decoration-none">{data.company.website}</a>
                        {/if}
                    </div>
                </section>

                
                
                <section class="mt-4">
                    <h6 class="text-uppercase text-primary">Skills</h6>
                    <h5>
                    {#each data.personal.skills.frontend as skill (skill)}
                        <span class="badge bg-secondary mt-2" style="margin-right: .5rem;">{skill}</span>
                    {/each}
                    </h5>
                    <h5>
                    {#each data.personal.skills.backend as skill (skill)}
                        <span class="badge bg-secondary mt-2" style="margin-right: .5rem;">{skill}</span>
                    {/each}
                    </h5>
                </section>
                
                <section class="mt-4">
                    <h6 class="text-uppercase text-primary">Languages</h6>
                    <h5>
                        {#each data.personal.languages as language (language)}
                            <span class="badge bg-secondary mt-2" style="margin-right: .5rem;">{language}</span>
                        {/each}
                    </h5>
                </section>
            </div>
        </div>
    </div>
</main>

<style>
    .img-profile{
        width: 100%;
        filter: grayscale(70%);
    }

    @media (min-width: 576px) {
        .img-profile{
            width: 12rem;
        }   
     }

    @media print {
       .print-8 {
        flex: 0 0 auto;
        width: calc(8 * (100% / 12));
       }
       
       .print-4 {
        flex: 0 0 auto;
        width: calc(4 * (100% / 12));
       }
    }
</style>