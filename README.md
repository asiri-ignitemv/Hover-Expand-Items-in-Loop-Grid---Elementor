### Add Class to Main Container

    kv-card

### Add Class to Sub Container

    kv-overlay

### Add Class to Visible Title

    kv-title

### Add Class to Invisible Description to show when hover

    kv-desc

### Add CSS to Main Container

   

    selector {
        overflow: hidden;
    
        background-size: cover;
        background-position: center;
    /*background-position: center 60%;*/
        transition: background-position 0.6s ease;
    }
    
    /* =========================
       OVERLAY
    ========================= */
    selector .kv-overlay {
        position: relative;
        isolation: isolate;
    
        padding-top: 50px;
    
        transition: padding-top 0.5s ease;
    }
    
    /* Gradient layers */
    selector .kv-overlay::before,
    selector .kv-overlay::after {
        content: "";
        position: absolute;
        inset: 0;
    
        z-index: -1;
        pointer-events: none;
    
        transition: opacity 0.5s ease;
    }
    
    
    /* =========================
       DEFAULT GRADIENT
       Transparent → Blue
    ========================= */
    selector .kv-overlay::before {
        background: linear-gradient(
            180deg,
            #002DB000 0%,
            #002DB0 100%
        );
    
        opacity: 1;
    }
    
    
    /* =========================
       HOVER GRADIENT
       Transparent → Blue → Yellow
    ========================= */
    selector .kv-overlay::after {
        background: linear-gradient(
            180deg,
            #002DB000 0%,
            #002DB0 65%,
            #F4BD00 100%
        );
    
        opacity: 0;
    }
    
    
    /* =========================
       HOVER STATE
    ========================= */
    selector:hover {
        background-position: center;
        /*background-position: center 35%;*/
    }
    
    selector:hover .kv-overlay {
        padding-top: 60px;
    }
    
    /* Change gradient */
    selector:hover .kv-overlay::before {
        opacity: 0;
    }
    
    selector:hover .kv-overlay::after {
        opacity: 1;
    }
    
    
    /* =========================
       DESCRIPTION
    ========================= */
    selector .kv-desc {
        max-height: 0;
        opacity: 0;
        overflow: hidden;
    
        margin-top: 0;
    
        transform: translateY(10px);
    
        transition:
            max-height 0.5s ease,
            opacity 0.4s ease,
            margin-top 0.5s ease,
            transform 0.5s ease;
    }
    
    selector:hover .kv-desc {
        max-height: 300px;
        opacity: 1;
    
        margin-top: 8px;
    
        transform: translateY(0);
    }
