// ─────────────────────────────────────────────────────────────
//  Binek Porosity – GitHub Releases Fetcher
//  Automatically lists releases & pre‑releases from:
//  https://github.com/trabanttrump-source/Binek-Porosity
// ─────────────────────────────────────────────────────────────

const REPO_OWNER = 'trabanttrump-source';
const REPO_NAME  = 'Binek-Porosity';
const API_URL    = `https://api.github.com/repos/${REPO_OWNER}/${REPO_NAME}/releases`;

const container = document.getElementById('releaseContainer');

// ─── Helper: format date ───
function formatDate(iso) {
    const d = new Date(iso);
    return d.toLocaleDateString('en-US', {
        year: 'numeric',
        month: 'short',
        day: 'numeric'
    });
}

// ─── Helper: build download link ───
function downloadLink(asset) {
    // Prefer .exe if present, otherwise first asset
    const exe = asset.find(a => a.name.toLowerCase().endsWith('.exe'));
    const target = exe || asset[0];
    if (!target) return '#';
    return target.browser_download_url;
}

// ─── Render a single release ───
function renderRelease(release) {
    const isPre = release.prerelease === true;
    const isLatest = !isPre;  // we'll mark the first non‑pre as "Latest"

    const tagClass = isPre ? 'pre' : 'latest';
    const tagLabel = isPre ? 'Pre‑release' : 'Latest';

    // Get asset list (filter out source code zips if you like)
    const assets = release.assets || [];

    // Build download link (prefer .exe)
    const dlUrl = downloadLink(assets);

    // Manual PDF link (if present)
    const manualAsset = assets.find(a => a.name.toLowerCase().includes('manual'));
    const manualUrl = manualAsset ? manualAsset.browser_download_url : null;

    const div = document.createElement('div');
    div.className = 'release-item';

    // Left side: name + meta
    const info = document.createElement('div');
    info.className = 'info';

    const nameSpan = document.createElement('span');
    nameSpan.className = 'name';
    nameSpan.textContent = release.name || release.tag_name;
    info.appendChild(nameSpan);

    const metaSpan = document.createElement('span');
    metaSpan.className = 'meta';
    metaSpan.innerHTML = `
        <i class="far fa-calendar-alt"></i> ${formatDate(release.published_at || release.created_at)}
        &nbsp;&middot;&nbsp;
        <i class="fas fa-tag"></i> ${release.tag_name}
        &nbsp;&middot;&nbsp;
        <i class="fas fa-file-archive"></i> ${assets.length} asset(s)
    `;
    info.appendChild(metaSpan);

    // Tag (Latest / Pre‑release)
    const tag = document.createElement('span');
    tag.className = `tag ${tagClass}`;
    tag.textContent = tagLabel;

    // Right side: action buttons
    const actions = document.createElement('div');
    actions.className = 'actions';

    // Download button
    if (dlUrl && dlUrl !== '#') {
        const dlBtn = document.createElement('a');
        dlBtn.href = dlUrl;
        dlBtn.innerHTML = `<i class="fas fa-download"></i> Download`;
        dlBtn.target = '_blank';
        actions.appendChild(dlBtn);
    }

    // Manual PDF (if available)
    if (manualUrl) {
        const pdfBtn = document.createElement('a');
        pdfBtn.href = manualUrl;
        pdfBtn.innerHTML = `<i class="fas fa-file-pdf"></i> Manual`;
        pdfBtn.target = '_blank';
        pdfBtn.className = 'gh';
        actions.appendChild(pdfBtn);
    }

    // GitHub release page
    const ghBtn = document.createElement('a');
    ghBtn.href = release.html_url;
    ghBtn.innerHTML = `<i class="fab fa-github"></i> View`;
    ghBtn.target = '_blank';
    ghBtn.className = 'gh';
    actions.appendChild(ghBtn);

    // Assemble
    const topRow = document.createElement('div');
    topRow.style.cssText = 'display:flex;align-items:center;gap:12px;flex-wrap:wrap;';
    topRow.appendChild(info);
    topRow.appendChild(tag);

    div.appendChild(topRow);
    div.appendChild(actions);

    return div;
}

// ─── Main fetch ───
async function fetchReleases() {
    try {
        const response = await fetch(API_URL);

        if (!response.ok) {
            throw new Error(`GitHub API returned ${response.status}`);
        }

        const data = await response.json();

        if (!data || data.length === 0) {
            container.innerHTML = `<div class="error-msg">No releases found.</div>`;
            return;
        }

        // Clear loading state
        container.innerHTML = '';

        // Sort: newest first (already sorted by GitHub, but double‑check)
        const sorted = data.sort((a, b) => {
            const da = new Date(a.created_at);
            const db = new Date(b.created_at);
            return db - da;
        });

        // Render each release
        sorted.forEach((release, index) => {
            const el = renderRelease(release);
            container.appendChild(el);
        });

    } catch (error) {
        console.error('Failed to load releases:', error);
        container.innerHTML = `
            <div class="error-msg">
                <i class="fas fa-exclamation-triangle"></i>
                Could not load releases. Please try again later.
                <br><small style="color:#94a3b8;">${error.message}</small>
            </div>
        `;
    }
}

// ─── Go ───
fetchReleases();
