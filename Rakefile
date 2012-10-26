# encoding: utf-8

def config
  # in this Rakefile we can allow that
  $config ||= Hash.new
end

# main TeX file without extension
config['main'] = 'proposal'

# TeX command to invoke: xelatex, pdflatex, etc
config['latex'] = 'pdflatex'

# BiBTeX command to invoke, or nil if it is not necessary
config['bibtex'] = 'bibtex'


##############################################################################
# This Rakefile is written to simplify the compiling of
# LaTeX documents.
#
# v0.2.1 
# Use system instead of sh and call view inside pdf.
#
# v0.2.0
# Use `pdflatex` and reinvent the `config` method.
#
# v0.1.1
# Published as GitHub Gist, again.
#
# v0.1.0
# Code cleanup. Using `xelatex' as default command.
#
# v0.0.1
# Initial release.
##############################################################################

task :default => [ :pdf ]

desc 'Open the output PDF file'
task :view do
  unless Rake::Win32.windows?
    invoke 'open', "#{config['main']}.pdf"
  else
    raise NotImplementedError
  end
end

desc 'Build PDF'
task :pdf => [ :info, :clean] do
  
  latex '-draftmode', '-halt-on-error', '-shell-escape', "#{config['main']}.tex"
  if config['bibtex']
    bibtex config['main']
    latex '-draftmode', '-halt-on-error', '-shell-escape', "#{config['main']}.tex"
  end
  latex '-halt-on-error', '-shell-escape', "#{config['main']}.tex"
  Rake::Task["view"].execute
end

namespace :pdf do
  desc 'Build PDF in Draft Mode'
  task :draft do
    latex '-draftmode', '-halt-on-error', '-shell-escape', "#{config['main']}.tex"
  end
end

desc 'Cleanup'
task :clean => [ :trash ] do
  cleaner = proc { |path| rm_f(path) }
  [ 'aux', 'bbl', 'blg', 'toc', 'nav', 'log', 'out' ].each do |res|
    Dir.glob("*.#{res}", &cleaner)
  end
end

desc 'Trash created doc.pdf'
task :trash do
  rm "#{config['main']}.pdf" unless !File.exists?("#{config['main']}.pdf") 
end

desc 'Print configuration'
task :info do
  puts "Configuration: #{config.inspect}"

  has_latex = latex '--version' rescue false
  raise 'LaTeX is not installed' unless has_latex

  if config['bibtex']
    has_bibtex = bibtex '--version' rescue false
    raise 'BiBTeX is not installed' unless has_bibtex
  end
end


def rm(*args)
  invoke('rm', args)
end

def invoke(command, *arguments)
  args = arguments.flatten.map { |arg| "'#{arg}'" }.join(' ')
  system "#{command} #{args}"
end

def latex(*args)
  raise unless config['latex']
  invoke(config['latex'], args)
end

def bibtex(*args)
  raise ArgumentError unless config['bibtex']
  invoke(config['bibtex'], args)
end
