# ntfe

Not the fastest emulator

Computer
    Computer { CPU MemoryMap { RAM etc } IO }
    run (will run using whatever IO is defined)
        uses parser to ast from wherever it starts
        then uses each instruction from the ast to do whatever it is

    Probably going to be 6502 or Eater first
    then z80 / 8086 maybe idk

MemoryMap
    List of memory map locations
    { Mappable a => {
        part :: a,
        from :: Int,
        to :: Int
    )]}

AST
    6502
        Default vectors
        Interrupt routines
        Instruction = LDA a | etc
    Eater
        Default vector = 0
        Instruction = LDA a | 

Parser
    6502
        String -> AST
    Eater
        String -> AST

Cpu
    Eater (microcode)
        runAST :: AST -> [ThingsWhatHappened???] - invokes ucode
    6502 (define whatever)

IO (Mappable)
    Character for stdio
    Storage for files / ROMs etc
    Eater
        Stdio
        Graphical
        HTML etc
    6522
        Stdio
        Graphical
        HTML etc
Gpu
    SVGA
    CustomOldGpu
Sound
    Something